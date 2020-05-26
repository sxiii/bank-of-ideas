## MetaPass: Password Control & Security

## Project brief description
Online, web-first automated password management toolkit.
Entry to the system might be made to be as hard and as many factors as user like.

## Project full description
Through 20 years of effort, we've successfully trained everyone to use passwords that 
are hard for humans to remember, but easy for computers to guess.

Basic ideas behind the project:
* Access to the platform should be allowed by using auto-rotating, super-hard-to-guess password & mask
* Access to the platform needs to be flexibly protected by as many additional factors, as user want (2? 3? 5? 10? 20?)


## Different factors for authentication to platform
MetaPass allows you to choose as many factors as you like. Also, each factor can have any specified amount
of time to acomplish. To be prepared to using of the auth process to MetaPass, user should pass the "auth training"
by verifying two times that he remembers his auth process.
1) Passwords or passphrases - as many as user want and as long as user want. Also they can have text, audio, video, or everything as hints.
2) Passwords can contain automatically changing parts or "masks". For example, your password is "p4ssw0rD" and today is 01.01.2020; you can make resulting password, for example: 01.01.2020#p4ssw0rD
3) YubiKey or similar physical devices - as many as user want
4) File auth - you need to attach specific file as additional factor (files up to X megabytes; then they are checksummed and used as additional factor)
5) Secret URL on the service - navigate to it (ideally, nobody knows about it) to continue auth process
6) SMS code auth (we send you the code)
7) Auth by email: MetaPass send you either "accept link" to your email, the "accept code", or both. You might be also asked no leave the page open while auth goes (similar to blockchain.com auth)
8) Robot call audio auth (robot tell you the code by generated voice)
9) Robot calls and asks you to type-in your "phone security PIN" (can auto-apply auth or tell you resulting code to type-in on the MetaPass platform) 
10) "Honeypot" or "error" login protection at any point during auth. What this point means, is that user can 
configure the look and feel of "an error", while AUTH went okay - you just need to press in specific place of the page
or navigate specific URL.
11) Skill proof feature. This can be made as a mini-game, in which user has to achieve some specific score (say: 1000). Minigame should be hard enough for newcomers to achieve this score.
*) Additional "auth factors" can be proposed and added by users via GitLab/Github etc.

Each of the protection measure/factor should have some "security points" assigned to it (example: SMS auth should be considered the less safe and add you only 1 security points).
Based on the points we can then tell user, how safe is their set-up.

By default system should recommend user to set-up at least 3 to 5 steps auth.
* 3 to 5 auth steps should be considered as minimum security (5 to 15 points)
* 6 to 9 auth steps should be considered as good security (16 to 25 points) 
* 10 to 13 auth steps should be considered high security (26 to 35 points)
* 14 and up auth steps should be considered extra security (36 or more points)

## Additional ideas for the future auth methods
11) If we can make 99% exact neural network which detect user's photos, we could use it as factor.
12) If we can make 99% exact neural network to detect user's voice, we could use it as factor.
13) Robot call with voice recognition (check the previous point).
* Each step of the AUTH process can be marked by specific color and word that you like. It will be shown during the process.
* Auth process can be automatically shuffled in random way. Let's say you have 7 auth factors, they will all come at random order.

## Flexible blocking
* If the user (or the attacker, we don't know that, right?) cannot login specified times (default: 4), he got banned for T (T=specified time, example: 4 hours).
* If the user (or the attacker) cannot login after time-out 4 times more, we make NEW_BAN_TIME=T*x where X can be setted up by the user (default = 4, so it will be 4*4=16 hours of bantime)
* What to do after third time fail condition should be either prolonguing even more (example: T*x^x) or blocking account for manual check-up or starting some security measure (e.g. auto-changing all the passwords and blocking account or something like that)

## What is next? What's happening after auth? Functions?
User get access to his password vault with the following functions:
* Saving, viewing and changing passwords in the database (manually)
* Setting up AUTH and PASSCHANGE system robots
* Login scheduling: you can set-up the login templates for external websites & services (e.g. "work", "social", "games", "streaming", "fakes", etc.). Then with 1 click you can be automatically logged in by AUTH robots into all of websites under specified category. You can even select multiple categories.

## What are MetaPass system robots?
* AUTH robot: it allows you to press 1 button in the system, and it logs-in you automatically to your desired accounts.
* PASSCHANGE robot: it allows you to automatically change you password in specified service without touching it at all.
Developers should have API to write their own AUTH and PASSCHANGE robots.

## Additional docs & info on the project
* Project was announced in 2015 as "MetaPass" in Russian Hackathon @ Rostov-on-Don, presentation from that hackathon: 
...
If you believe FAKETEMP project idea is good, please visit the website and star my github repo. Thank you.

![Password_strength](https://imgs.xkcd.com/comics/password_strength.png)

## Author
Please link the author - @sxiii. 

## License
Preferably the GPLv3 or similar.

## Links
* Website: N/A
* Github: N/A
