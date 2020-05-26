## MetaPass: Password Control & Security

## Project brief description
Online, web-first automated password management toolkit.
Entry to the system might be made to be as hard and as many factors as user like.

## Project full description
Through 20 years of effort, we've successfully trained everyone to use passwords that 
are hard for humans to remember, but easy for computers to guess.

Basic ideas behind the project:
* Access to the platform should be allowed by using auto-rotating, super-hard-to-guess password & mask
* Access should be flexibly protected by as many additional factors, as user want (3? 5? 7? 10? 15?)
* When user successfully logs-in, he can manage the passwords and set-up automated bots for this feature
* Another use-case for the platform is one-click sign-in into any list of specified services via templates & auth robots, as long as automated scheduled password changed (you can even change your passwords every day, if you like)

## Different factors for authentication to platform
MetaPass allows you to choose as many factors as you like. Also, each factor can have any specified amount
of time to acomplish. To be prepared to using of the auth process to MetaPass, user should pass the "auth training"
by verifying two times that he remembers his auth process.
1) Passwords or passphrases - as many as user want and as long as user want. Also they can have text, audio, video, or everything as hints ('static password')
2) Passwords can contain automatically changing parts or "masks". For example, your password is "p4ssw0rD" and today is 01.01.2020; you can make resulting password, for example: 01.01.2020#p4ssw0rD ('dynamic password')
3) YubiKey or similar physical devices - as many as user want
4) Code generation apps - as many as user want - and allowing manipulations that needs to be done by the user to log-in (check "SMS code auth #7" idea for explaination)
5) File auth - you need to attach specific file as additional factor (files up to X megabytes; then they are checksummed and used as additional factor)
6) Secret URL on the service - navigate to it (ideally, nobody knows about it) to continue auth process
7) SMS code auth (we send you the code) with one or multiple SMS codes. They also might need to be merged ("1234" + "5678" = 12345678") or calculated ("1234" + "5678" = "6912") by user before sending. Calculation steps are submitted by the user (can be: addition, subtraction, multiplication, division (with round-up), rooting, etc.)
8) Auth by email: MetaPass send you either "accept link" to your email, the "accept code", or both. You might be also asked to leave the page open while auth goes (similar to blockchain.com auth)
9) Robot call audio auth (robot tell you the code by generated voice)
10) Robot calls and asks you to type-in your "phone security PIN" (can auto-apply auth or tell you resulting code to type-in on the MetaPass platform) 
11) User call (mobile/wire/skype/telegram/zoom/etc): you need to call some specified or secret number and type-in secret combination or listen to the code. Calls can be audio, video, or both.
12) "Honeypot" or "error" login protection at any point during auth. What this point means, is that user can 
configure the look and feel of "an error", while AUTH went okay - you just need to press in specific place of the page
or navigate specific URL.
13) Skill proof feature. This can be made as a mini-game, in which user has to achieve some specific score (say: 1000). Minigame should be hard enough for newcomers to achieve this score. Also the best here, is that you can specify the exact points at which you need to DIE or EXIT game to successfully log-in. Even better, you might request some exact amount of points that can be gathered only by multiple plays of the game (say, you can earn 1000 points in one game, but you need 3666 points for login to succeed). In this example, you need to "win" the game fully 4 times, and at 5th playthrough, stop playing at the moment when you reach score 666. This exact amount of points to log-in should be hidden from hacker.
14) CryptoPayAuth and FiatPayAuth: you can set-up a specific wallet that needs to receive specific amount of money to log you in. Example: you need to send 0.01234 ETH to Your_Secret_wallet. System monitors transactions and when the money arrives, this step is done. The amount that needs to be transferred can be: generated at login randomly but in limits (ex: from 0.000001 eth to 0.009999 eth), fixed by you and visible while logging in, fixed by you and invisible while logging in. Instead of ETH, we might have any Crypto, or even Fiat if the service you want to use has API. Amounts are usually transferred between your own wallets (so you pay 0 or only network/transfer comissions), but you can also set a donation into a "MetaPass system login" wallet instead. NOTE: This step might slown down log-in dramatically.
15) Other already logged-in accounts: user might need to be logged to any number of social networks or accounts (example: facebook, google and reddit) to proceed
16) Social post: user can be requested to make a post to one or multiple social networks with auth text. Auth text can be randomly generated by system based on templates or specified by user secretly.
17) Text bot verification: user need to send a secret code to service's bot in IRC, Jabber, Telegram, Wire, etc.
18) Secret email verification: user needs to send email to system's address. The email should contain secret text specified by user or text generated by system based on templates & upon login.
19) Signing a text message or file: user is requested to sign a system-generated message (or file) with his private key and send the result to the system. If user has access to his private key, we can verify that HE ACTUALLY IS the message signer by using his publik key. This is the example approach used in Bitcoin and other Cryptocurrencies everywhere.
20) Asking another MetaPass user to approve your login attempt. This step is done from his/her MetaPass account after successful login. It can be your family member or your friend, for example.
*) Additional "auth factors" can be proposed and added by users via GitLab/Github etc.

* Each auth factor can have text, audio, video, or everything both as hints or misleads/distractions.
* Ideally, system needs to encrypt all the data inside the database additionally on CLIENT-SIDE by utilizing double-password approach, similar to the double-password security measure approach from ProtonMail email service.
* System can show current step number, total step number, both, or FAKING the step numbers to mislead the attacker.
* Each auth factor should be as hard as possible for robots to go through.
* Auth can be time-locked. As example, you might be permitted to login only from 12:00:00 to 16:30:00 by UTC time. In case you are trying to login in the wrong time, you might got "fair" error (wrong login time), or "fake" error which will mislead attacker (e.g. wrong password, system error, etc.).
* It should be possible for user to set up a "disaster recovery" plan: what will happen if he/she cannot pass some auth methods. For example, he can replace one or multiple auth steps with another steps by going into secret URL or requesting system for this behavior at some point. Especially this step is important for unstable auth plugins like "CryptoPayAuth" or "FiatPayAuth" modules.

Each of the protection measure/factor should have some "security points" assigned to it (example: SMS auth should be considered the less safe and add you only 1 security points).
Based on the points we can then tell user, how safe is their set-up.

By default system should recommend user to set-up at least 3 to 5 steps auth.
* 3 to 5 auth steps should be considered as minimum security (5 to 15 points)
* 6 to 9 auth steps should be considered as good security (16 to 25 points) 
* 10 to 13 auth steps should be considered high security (26 to 35 points)
* 14 and up auth steps should be considered extra security (36 or more points)

As you can imagine, the security of log-in process into the MetaPass system can be much more safe, than accessing secret service database or launch codes for nuclear rockets. You can set-up the security so high (example: 40 log-in steps), that even you, yourself, will be prevented from logging-in most of the time, if you wanted to. Also, you can set the account security to not so high level, but to count on lazyness of the hacker. In this case, you can ask to win the small game during log-in session (example) 20 times, which might be annoying and time-consuming for hacker.

## Additional ideas for the future auth methods
* If we can make 99% exact neural network which detect user's photos, we could use it as factor.
* If we can make 99% exact neural network to detect user's voice, we could use it as factor.
* Robot call with voice recognition (check the previous point).
* Each step of the AUTH process can be marked by specific color and word that you like. It will be shown during the process.
* Auth process can be automatically shuffled in random way. Let's say you have 7 auth factors, they will all come at random order.

## Importance of misleading
Each of performed auth step might be followed up either by TRUE information (e.g. you are on step 3 out of 4 in your auth process) or by FALSE information (e.g. error: security auth failed on step #3 which does actually means that security auth went OKAY and you might proceed to the next step!). This misleading should be there to make it much harder for attacher to get into your account even if he knows all your information, masks, passwords, etc. etc. You can specify each step, it's description and information that is given to the user during process.

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

## Monetization
* Factors, that are more expensive than others (example: robot calls) can be limited to paying subscribers
* Free account might be limited with max number of allowed auth steps. For ex., each factor can be used only 1 time.
* Automated password change might be limited for free users (e.g. 2 automated password change for every service for free per year)
* Free users can have maximum number of external services connected (or automated), example: 100 services max.

## Additional docs & info on the project
* Project appeared as idea and was drafted in 2015~2017 by @sxiii
* Project was publically announced in 2018 as "MetaPass" at "47hours" Russian Hackathon @ Rostov-on-Don, presentation from that hackathon: http://bit.ly/metapassword

![Password_strength](https://imgs.xkcd.com/comics/password_strength.png)

## Author
Please link the author - @sxiii. 

## License
Preferably the GPLv3 or similar.

## Links
* Website: N/A
* Github: N/A
