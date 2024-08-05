
 
In the meanwhile: a lot of forth and back discussion about the Oracle-owned trademark on "Java"; ultimately the Eclipse Foundation had to rename "Java EE" to "Jakarta EE" all over place, including the source code and the documentation.
 
**Download Zip 🗹 [https://amreamate.blogspot.com/?d=2A0T0o](https://amreamate.blogspot.com/?d=2A0T0o)**


 
It was originally also planned to bump the minimum required Java SE version from 8 to 11, however in the end it turned out to be less than trivial to make the existing GlassFish server, still considered the "reference implementation", compatible with Java SE 11. Due to the time constraints and lack of GlassFish committers, Jakarta EE 9 was stuck at Java SE 8.
 
Here's an overview based on Faces 4.0 milestone of what's changed in Faces 4.0 as compared to Faces 3.0 which is in turn basically exactly the same as JSF 2.3 but then with "javax" renamed to "jakarta" all over place.
 
#1546: JSP support was for the first time deprecated in JSF 2.0 (Dec 2009) in favor of Facelets, because the JSP life cycle did not fit very well in the JSF life cycle. The core issue was that JSP writes template text to response as soon as it was encountered during the view build time, while it should be postponed to the render response phase, causing the developers to fiddle around with tags and/or forcing themselves an unnecessary "everything must be a JSF component" mindset. JSP support was during JSF 2.x and 3.x maintained as backwards compatibility for old JSF 1.x applications whose JSP pages need to be gradually migrated to Facelets.
 
With Faces 4.0, JSP support is now finally physically removed. This means that it is not anymore possible to use JSP as a view technology for Faces. It's thanks to the enormous pluggability of Faces theoretically still possible to maintain JSP support via an external library with custom ViewDeclarationLanguage, ViewHandler and StateManager implementations, but this is clearly not recommended.

In hindsight, this was actually a mistake, because around the same time CDI was born and offered the same functionality via @Named and friends. See also Is @javax.faces.bean.ManagedBean Dead on Arrival? It was unfortunately too late to switch from @ManagedBean to @Named before the JSF 2.0 release, so the @ManagedBean sticked around for a bit of time, perhaps to the joy of Spring/Tomcat/Jetty based custom stack adepts. The @ManagedBean and friends were ultimately officially deprecated in JSF 2.3 in favor of CDI and are now completely removed.
 
#1548: During JSF 1.0 development around 2004, a bunch of things were missing in the existing standard EL (Expression Language) spec, such as auto-creation of objects (managed beans) and being able to call setter methods instead of only getter methods. So a kind of an extension to the existing EL spec was added in flavor of javax.faces.el.\* package. With this extension, JSF pages can use #... instead of $... if managed beans should be auto-created and/or if bean properties should be set instead of get (via input components) and/or if JSP should be prevented from immediately evaluating those expressions (in case JSP is used instead of Facelets).
 
This functionality was ultimately unified with standard EL as part of JSP 2.1 during JSF 1.2 development around 2005. The classes in the javax.faces.el.\* package were therefore since JSF 1.2 deprecated in favor of the new classes in the javax.el.\* package. Among them are the known MethodBinding and ValueBinding classes, which more than often unexpectedly surface when you as Faces developer want to create a custom component. They are now finally removed.
 
In hindsight, this alternative way should never have been introduced as it not only caused confusion but was also less thread-safe. Hence these constants were deprecated right away in JSF 2.1 maintenance release shortly following JSF 2.0. Now they are removed.
 
#1578: The StateManager was polished a lot since JSF 1.0 and thereby left behind a trail of deprecated methods growing longer almost every new JSF version. These are now all removed as part of a major clean up for the fresh new Faces 4.0.
 
#1583: The ResourceResolver was inherited into JSF 2.0 as part of the original version of Facelets. It basically offered a way to obtain a reference to an URL to a physical Facelets file based on a given path, so that one could get e.g. "last modified" timestamp or even an input stream out of it. However, at the same moment, in JSF 2.0, the ResourceHandler class was introduced which is able of doing more or less the same thing, obtaining a reference to a "resource" based on a path, but it was not possible to obtain an URL from it. Still, there was a big overlap in the functionality and this caused confusion.
 
In JSF 2.2, the ResourceHandler#createViewResource() method was finally introduced for the very purpose of (indirectly) obtaining a referece to an URL to a physical Facelets file based on a given path, so the ResourceResolver could be deprecated. It's now finally removed.
 
#1552: With the rename of the Java EE brand to Jakarta EE, "JavaServer Faces" was promptly renamed to "Jakarta Server Faces". It was originally intended to also drop the "Server" part from the name in order to simplify the name and to remove the need for an abbreviation (which people would only keep questioning the full form for), but that slipped through during the chaos. With Faces 4.0, we have now the opportunity to completely drop the "Server" part and the "JSF" abbreviation. The full name is now "**Jakarta Faces**" and the short name is just "**Faces**". The package root and the Maven coordinate and the base name of the JAR file were already "jakarta.faces", so that leaves basically only the variable and file names in public API open for the rename.
 
#1553: The XML namespace URIs could of course not be left untouched during the big rename of "JSF" to "Faces" as they still contain the /jsf part. We however went a step further: the URL form of " \*" was also converted to the URN form of "**jakarta.faces.\***". This was primarily because they did not and will never represent real web addresses and people keep getting confused on why they resemble a web address and why they couldn't find anything over there and why there did not seem to be any XSD documents backing them. They were just URLs in first place because it was during the 90s the norm to use whole URLs as namespace URIs, as you can also see in good ol' JSP files with those which actually also never existed as real web pages and never had something like XSD documents.
 
With this change, this eternal confusion and potential future renames should be stopped, hopefully for good. Similarly, the " \*" namespace URIs of Jakarta Tags (formerly known as JSTL) are in Jakarta Faces also converted to "**jakarta.tags.\***", see also jstl-api#144. Summarized, here are the new XML namespace URIs:
 
Noted should be that Faces 4.0 still recognizes previous XML namespaces for sake of backwards compatibility, even the original " \*" ones where applicable. You can find below an useful overview of package names and XML namespace URIs used across the time:
 
This was however unnecessary when a HTML5 doctype was used because those values are then already implied as the default values. A sane HTML5 validator will emit warnings on this. Since Faces 4.0, when a HTML5 doctype is used, the default renderers of and will automatically skip the type attribute as in:
 
And you change only one of them, then you'd intuitively expect that all the three dropdowns "day", "month" and "year" are processed (applied, converted and validated) during the Faces Ajax request, basically "the whole composite component". However, in reality only the dropdown which the end user interacted with is processed, and the other two were not processed at all. This does not match the expectation of execute="@this" and might give skewed behavior during any customized conversion and validation within the composite component's implementation.
 
#1570: The SameSite attribute was proposed around 2016 and introduced in Google Chrome. Basically, it was yet another measure against CSRF and phishing attacks which kind of exploded around that time. Imagine the following use case:
 
When the SameSite attribute is set to Strict or Lax, then the user won't anymore be able to resume the existing session cookie. This is particularly inconvenient when your site needs to redirect to a 3rd party site which then redirects back to your site, more than often to perform a payment. The solution would be to set SameSite attribute to None on the cookie(s) relevant to the resume.
 
When the SameSite attribute is set to Strict, then the user won't anymore be able to resume the existing session cookie. This is particularly inconvenient when the iframe needs to redirect to a 3rd party site which then redirects back to your site, more than often to perform a payment. The solution would be to set SameSite attribute to Lax or None on the cookie(s) relevant to the resume (or to simply switch to a modern and transparent API client running in the backend so that there is no need at all for an iframe ;) ).
 
Since February 2020, Google Chrome has bumped the default value of SameSite from None to Lax, causing a bit of panic in web development world. This is where all the trouble started with particularly Servlet based web applications, because the Servlet Cookie API did not offer any way to set a custom attribute. Adding a way to the Servlet API spec was yet more troublesome, because the SameSite attribute is to the day of today still in draft mode and still not included in the standard HTTP cookie spec. The Servlet API guys did not like their spec to be dependent on a moving target and hence the long-demanding Cookie#setSameSite() method (it was requested for the first time on May 2017) couldn't be introduced without potentially getting broken