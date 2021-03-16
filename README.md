# LB-QLC-Control
This QLC+.lbe is a LioranBoard extension to control Q Light Controller Plus software using webSockets

**What is [LioranBoard](https://obsproject.com/forum/resources/lioranboard-stream-deck-animator.862/)?**
LioranBoard is a completely free and fully customizable stream deck, which can be used both on PC and Android devices. It can control OBS (OBS Websocket plugin required) and can be connected to Twitch to allow your viewers to directly control your stream or to set up custom alerts. It can also play sound clips, simulate keypresses (macros), and send command line commands.

**What is [QLC+](https://www.qlcplus.org)?**
QLC+ is a free and cross-platform software to control DMX or analog lighting systems like moving heads, dimmers, scanners etc.

This extension is based on WebSockets and communicates with QLC+ using QLC Web API 
QLC+ Web API: https://www.qlcplus.org/Test_Web_API.html
By This plugin you can set functions containing EFX, scenes, collections via your LioranBoard Streamdeck or Twitch points

Options:

![](https://cdn.discordapp.com/attachments/592354121479356448/821528110654554112/unknown.png)
`Set Function` - Sets a function to be turned on, turned off, toogled with forcing other scenes to be turned off or not

Parameters:
1. `FunctionId` - Id of the function (You can see a list of functions on tsl_transmitter.html page, QLC+ section).
2. `Visible` - Turn On, Turn Off or toogle.
3. `ForceOthersToStop` - Variable to decide if you want to turn off other functions off and leave only this one as active.

`Get Function Status` - Gets a status of the function as Running, Stopped or Undefined
![](https://cdn.discordapp.com/attachments/592354121479356448/821528719696986132/unknown.png)
Parameters:
1. `FunctionId` - Id of the function (You can see a list of functions on tsl_transmitter.html page, QLC+ section).
2. `Variable` - Variable to put function status.
