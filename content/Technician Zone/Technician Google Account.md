The FabSoc Technician Google Account, more commonly referred to as just the *Technician Account* is the account that is used for accessing a number of FabSoc resources that require a google account login including but not limited to:
- Technician Email Access
- [[Accessing Bambu Labs Printers]]
- Tailscale Network

This is a publicly accessible page so no specific passwords will be listed here but I can supply links to where they are detailed in the FabSoc exec channels - You'll only be able to access these if you are a technician or higher in the fabrication society discord!

## How to login
First from the google login screen, enter the email and password as you normally would:
- Email: technician@fabrication.activateuts.com.au
- Password: [Technician Link😺](https://discord.com/channels/1038007666032787476/1215834349065469992/1224556561939173427)

You will then be asked for the 6-Digit, 2FA Key - however the login page will word this as a *Verification code from the **Google Authenticator App*** - YOU DO NOT NEED TO USE GOOGLE AUTHENTICATOR
![[Pasted image 20250915171506.png]]
When you reach this stage you will need to setup a two factor code generator, This is an app which will take the 2FA ***Key*** and turn it into 6-Digit 2FA ***Code***s that google needs to let you login. For this guide I will be using the Ente Authenticator as it is free, open source and available on all the main platforms (Android, iOS, Windows, Mac and Linux). The Instructions should be fairly similar regardless of the platform you use 
### Setup Ente (Android App)
1. Download the Ente Authenticator: https://ente.io/download/
2. When you open the app you will be asked if you want to login to an account, You can do that id you want but for this guide I will not be logging in and instead pressing "Use without backups"
   ![[Pasted image 20250915173509.png|300]]
3. Select "Enter a setup key"
   ![[Pasted image 20250915173548.png|300]]
4. Fill in the fields for the new account
   Issuer: `Google`
   Account: `Technician Account`
   Secret: The 2FA ***key*** which is available to view here: [Technician Link😺](https://discord.com/channels/1038007666032787476/1215834349065469992/1417051789878104195)
   ![[Pasted image 20250915173816.png|300]]
5. You now have access to the generated 2FA ***codes***! This is what you enter into the google login.
   ![[Pasted image 20250915173851.png|300]]


> [!Warning]- Why have we set it up like this?
> tldr: google doesn't trust us.
> 
> A standard google account (the technician account) is not intended to be used by more than one person. Because we have the account shared between many people, google becomes very suspicious that we are up to no good. As a result it requires some sort of authentication so that it is content that it is really us. If we attempt to switch off all 2FA then we are blocked from logging in so we have to enable at least something, and the 2FA Code/"Google Authenticator" is the easiest way to do so that can still be shared between all the technicians 


> [!DANGER] Warning
> Do not login to the technician account from any google app on your phone. Doing so will enable google prompt which means that whenever someone else tries to sign into the account, you will receive a prompt on your phone to allow or deny their login attempt. Not only would this be annoying for you but it also means that other technicians cannot access the account without you allowing them
> > [!Failure]- What do I do if I've enabled google prompt
> > To disable google prompt you will need to remove all mobile phones attached to the google account to disable it, there are two main methods:
> > 1. From the phone that is logged in, go to google account settings and remove the technician account
> > 2. From the google account admin (any device), go to devices and force sign out all mobile devices - however this method will most likely trigger a google prompt challenge (It is possible to avoid challenges if you are at UTS since the system will be less suspicious of your login attempt)

