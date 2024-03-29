_PSPunch is in a super limited Proof of Concept state right now. A lot of this README is place holder indicating where the project will be at when it's "done". It's under heavy, active development and should be taking shape rapidly, with a "1.0" release planned early 2016. I'm writing an ongoing series of articles about where this project (and it's parent, [PS>Attack](https://github.com/jaredhaight/)) is at [here](https://www.psattack.com/articles/20150212/psattack-v000001/)_

_If you have any questions or suggestions for PS>Attack and PSPunch, feel free to reachout on [twitter](https://www.twitter.com/jaredhaight) or via email: jaredhaight `at` prontonmail.com_

## PSPunch
An offensive Powershell console aimed at making Windows pentesting a little easier.

#### What is it
PSPunch combines some of the best projects in the infosec powershell community into a self contained executable. It's designed to evade antivirus and Incident Response teams.

1. It doesn't rely on powershell.exe. Instead it calls powershell directly through the dotNet framework.
2. The modules that are bundled with the exe are encrypted. When PSPunch starts, they are decrypted into memory. The unencrypted payloads never touch disk, making it difficult for most antivirus engines to catch them.

Offensively, PSPunch contains commands for Privilege Escalation, Recon and Data Exfilitration. It does this by including the following modules and commands:

* [Powersploit](https://github.com/PowerShellMafia/PowerSploit)
  - Invoke-Mimikatz
  - Invoke-GPPPassword
  - Invoke-NinjaCopy
* [PowerTools](https://github.com/PowerShellEmpire/PowerTools)
  - PowerUp
  - PowerView

#### How to use it
PSPunch works best when you generate your own version through [PSAttack](https://www.github.com/jaredhaight/PSAttack). PSAttack will handle downloading PSPunch, updating the modules to the latest versions, encrypting them with a custom key and then compiling the whole thing into an executable.

If you want to just try PSPunch, you can download a compiled release from the [releases](https://www.github.com/jaredhaight/PSPunch/releases/) tab. This binary will work, but the modules may be out of date and the encrypted files aren't custom so they're going to be much easier to spot by AV or IR teams. 

Of course, you can also just clone the repo and compile the code yourself. You can use Visual Studio Community Edition to work with it and compie it.

#### Gr33tz
PSPunch was inspired by and benefits from a lot of incredible people in the PowerShell community. Particularly [mattifiestation](https://twitter.com/mattifestation) of PowerSploit and [sixdub](https://twitter.com/sixdub), [engima0x3](https://twitter.com/enigma0x3) and [harmj0y](https://twitter.com/HarmJ0y) of Empire. Besides writing the modules and commands that give PSPunch it's.. punch, their various projects have inspired alot of my approach to PSAttack and PSPunch as well as my decision to try and contirbute something back to the community.

A huge thank you to [Ben0xA](https://twitter.com/ben0xa), who's [PoshSecFramework](https://github.com/PoshSec/PoshSecFramework) was used to figure out a lot of things about how to build a powershell console.
