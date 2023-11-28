# WebSandBox
A secure way to display a web page in kiosk mode using Windows Sandbox

## Motivation
I need to display a specific web page in kiosk mode on thousands of PCs running in a domain. I don't want the web page to interact with any part of the operating system that could reveal the identity of the user ( because I simply don't trust the remote web page ). 

## How it works
Enable Windows Sandbox by following instructions here :

https://learn.microsoft.com/en-us/windows/security/application-security/application-isolation/windows-sandbox/windows-sandbox-overview

Simply download the file [wgLaunchWebsiteInSandbox.wsb](https://github.com/citron/WebSandBox/blob/main/wgLaunchWebsiteInSandbox.wsb) and double click on it.
It invokes Microsoft Edge in a fresh Windows Sandbox and launches the web page https://gacquer.com/golivego/the_hu.html which is a simple maximised iframe running an amazing video from the very first captured concert of the great mongolian band [The Hu](https://www.thehuofficial.com/). The youtube video is autoplayed thanks to the switch "--autoplay-policy=no-user-gesture-required" applied to msedge and the specific configuration in the HTML file, also given for reference as *the_hu.html*
![Capture d'écran 2023-11-28 220908](https://github.com/citron/WebSandBox/assets/161367/5cb5a532-2a81-4046-a99a-3760f25bc1c1)
## Is this secure ?
As secure as Windows Sandbox can be. While the File system is protected, the network is still unprotected. I am waiting for Microsoft to give us a way to apply firewall rules to a sandbox. The user can't copy and paste between the sandbox and the mother OS.

## Next steps
- Write a GPO to deploy the script on all PCs from the domain
- Launch the sandbox automatically
- Point to an URL which will download a Webassembly program that creates a slave worker. This worker uses local sandboxed GPU and CPU power to compute any scientific task that will save the world. This approach is much more secure than [BOINC](https://boinc.berkeley.edu/)

## Why do I do all that ?
Because my employer -a big hospital- asks me to do miracles with a single GPU on my laptop when I need tens of NVIDIA H200 to train huge models. I saw the 6000 PCs doing nothing but waiting for something to happen. I suggested to use BOINC on them but it was refused for security reasons. Now I have the power to ask billions of PC to contribute to science... or coin mining... but I will not... or maybe a bit... just a joke. 





