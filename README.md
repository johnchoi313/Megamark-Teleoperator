##Tele-Robotic Avatar with Choitek Megamark and Agora IO!##

*Agora IO Hackathon 2018 Submission*

![](Cameras.jpg)

## Inspiration
The ultimate goal of COMMUNICATION is broadly defined as the *"means of connecting people and places in particular."*

As history can attest, each phase of communication technology developed has revolutionized the world in ways unimaginable to the generation directly preceding it. In the beginning, it was the invention of spoken language. Then, still several thousand years ago, *written* language. In the early days of the Enlightenment, the printing press made spreading ideas across nations much quicker and easier. In the Industrial Revolution, the telegraph and telephone made global communication instantaneous. In the Atomic Age, remote television made live streaming a reality, allowing millions to see the surface of the moon with their own eyes. And in the modern day, the Internet changed everything.

What's next in the story of human communication?

We believe telepresence is the defining next chapter - emulating the ability to see, think, hear, and feel a remote environment without actually being there. Recent advances in tele-robotics and virtual reality technology have allowed us to become tantalizingly close to this final vision. Our submission to the Agora IO Hackathon 2018 gives you a quick and friendly sample of this dream, made possible with the incredible streaming technology of Agora IO!

## What it does
We've built a telepresence app that allows to you remote pilot a Choitek Megamark mobile manipulator robot from anywhere in the world with a stable and high speed internet connection, enabling the user to physically operate in remote environments while increasing awareness of the surroundings beyond that of a traditional video call. The Choitek Megamark features a mobile base, a laptop-for-face for easy setup and a two arms with simple grippers for doing basic tasks. *(Note to judges: robotic hardware was actually developed prior to this hackathon, while the telepresence app software using Agora IO was developed during this hackathon.)*

![](RobotView.gif)

## How we built it

There are 3 primary ingredients in this demo, which are Unity the game engine, Arduino to control the robot, and of course the Agora IO SDK to handle live audiovisual streaming.

For this demo to work, there are two computers in question: one on top of the robot as the robot controller server, and the other computer as the remote viewer client. Then we follow the setup procedures as follows.

1. First, the user sets up the server laptop with the **Create Server** button and the appropriate credentials. *(Note: Strong high speed internet connection required! Choitek Megamark robot not required for basic video streaming. Call quality can be tested with the **Test Video/Audio Quality** button.)*

2. Then, once the robot server laptop has been setup, we open another instance of the app on the remote client viewer laptop, and fill in the same login credentials set on the robot server. This time, with the robot server running, we hit the **Join Server** button on the remote client. If the connection was successful, it should now be streaming audio and video between the laptops! *(Optionally, if a Megamark robot is connected to the robot server, keyboard commands will also be streamed from the remote client to the robot server to remote pilot the Megamark robot.)*

![](MegamarkTeleoperator.jpg)

## Challenges we ran into
Admittedly, while the app is functional, this standalone app is not production ready and has many chinks to work out before being ready for prime time:

- Unity version compatibility (using Unity 2017.3.1) out of date with official Agora IO SDK for Unity (optimized for Unity 5.5.2).
Although our hackathon project is functional, we had to do some *really* funky hacks to get it working (definitely not optimal solution and very slow and inefficient. Moving forward, we would love some help from official Agora team to get this patched with actual updated Agora IO SDK for latest Unity Version, as opposed to weird random hacks...)

- Video connection may randomly quit the call at higher resolutions. We believe this may be due to how we stream keyboard commands to control the Megamark robot, which is actually tied to another online gaming server service, which does not allow super high bandwidths (e.g. hi-res video) to be sent between two machines using said service. Also, Megamark robot control is still somewhat finicky and the Arduino may intermittently disconnect if the laptop's battery is low.

- Audio streaming is generates a lot of echos when using moderate volume, and is almost inaudibly quiet when lowering the volume - a happy medium is very hard to reach. We believe this is due to how we tied the streaming data from Agora to a Unity Audio Listener and Unity 3D Audio Source, which causes a strange feedback loop.

## Accomplishments that I'm proud of / What we learned 

We are proud of making a unique and fully functional mobile telepresence robot with a lot of good work on the hardware side *and* the software side, and combining the two into one beautiful chocolate-vanilla ice cream sundae (metaphorically speaking...)

![](ScifiHUD.gif)

In particular, we are proud of our clean-ish science-fiction starship UI, functional integration with robotics, telepresence, audiovisual streaming with keyboard command control and basic security, all working in a single standalone Windows-friendly executable. *(P.S. Try sticking on a 180-degree fish-eye lens on one of the laptop camera and enable the 3D-hemisphere rendering mode for super cool surround-view effect!)*

## What's next for Tele-robotic Avatar with Agora.IO!

Moving forward, we want to work out the chinks and make our telepresence app production ready and truly ready for prime time! 
- Optimize bandwidth consumption
- Allowing multi-user authentication
- Fixing that darn Microphone Echo!
- Improving the video quality and speed
- Add Virtual Reality Headset Streaming!
- Integrate an updated Agora IO for Unity! :D

