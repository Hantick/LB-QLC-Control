# LioranBoard Q Light Controller Plus Extension
This QLC+.lbe is a LioranBoard extension to control Q Light Controller Plus software using webSockets.

*You like the project? Please consider donating.* 

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=5HNJGX6SCWHLY)

**What is [LioranBoard](https://obsproject.com/forum/resources/lioranboard-stream-deck-animator.862/)?**

LioranBoard is a completely free and fully customizable stream deck, which can be used both on PC and Android devices. It can control OBS (OBS Websocket plugin required) and can be connected to Twitch to allow your viewers to directly control your stream or to set up custom alerts. It can also play sound clips, simulate keypresses (macros), and send command line commands.

**What is [QLC+](https://www.qlcplus.org)?**

QLC+ is a free and cross-platform software to control DMX or analog lighting systems like moving heads, dimmers, scanners etc.

This extension is based on WebSockets and communicates with QLC+ using QLC Web API 
QLC+ Web API: https://www.qlcplus.org/Test_Web_API.html
By This plugin you can set functions containing EFX, scenes, collections via your LioranBoard Streamdeck and LioranBoard triggers.

# Setup
To setup the extension simply install it on LioranBoard software.
To prepare QLC + you have to run the program with websocket flags. To do it simply run it with `-w` flag which means websockets have to be turned on.
Ref: https://www.qlcplus.org/docs/html_en_EN/commandlineparameters.html

Personally I prefer to create some `.bat` file with following command:
```
cd "C:\QLC+" (Path to your QLC)
start qlcplus.exe -w -p -o "C:/Path/YourWorkspace.qxw"
```
where:

`-w` - websockets

`-p` - program starts in performance mode

`-o` - program loads up a workspace on startup

Now you open LioranBoard software and run transmiter.html file (normally you would put it in OBS as a source)
On the transmitter page you can check your connection to QLC +
![image](https://user-images.githubusercontent.com/36815427/156151422-6f7696b8-1cb7-46c6-9d3e-683c3128e980.png)
Here you can load your defined QLC functions with corresponding IDs, which will be needed for using LioranBoard commands.

# Commands

![image](https://user-images.githubusercontent.com/36815427/156152154-f050e1f0-e9dc-4c0c-91ab-77cf41b6e3bf.png)
`Set Function` - Sets a function to be turned on, turned off, toogled with forcing other scenes to be turned off or not

Parameters:
1. `FunctionId` - Id of the function (You can see a list of functions on transmitter.html page, QLC+ section).
2. `Visible` - Turn On, Turn Off or toogle.
3. `ForceOthersToStop` - Variable to decide if you want to turn off other functions off and leave only this one as active.

![image](https://user-images.githubusercontent.com/36815427/156152191-e1a53671-b7e9-420e-9298-cce550378c82.png)
`Get Function Status` - Gets a status of the function as Running, Stopped or Undefined

Parameters:
1. `FunctionId` - Id of the function (You can see a list of functions on transmitter.html page, QLC+ section).
2. `Variable` - Variable to put function status.
