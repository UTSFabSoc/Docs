
> [!Warning] WIP
> - Tailscale
> - Domains 
> - Cloudflare tunnels
> - raspberry pi setup
> 	- diagrams?


In order to be able to connect to our printers from anywhere, we use a few different services and tools to allow access outside the Uni network

> [!NOTE] Note
> This only applies to non-Bambu Labs printers. They have their own solution for remote access. This document is specifically about tools used to connect to printers such as the Endermixer and Enderloop

## Connecting to the UTS Network
Since the 3D printers cannot be connected to the standard UTS network (since they require authentication), the printers will need to connect to DeviceNet. While device net is a controlled network, individual devices can be authorised via their unique mac address, usually this can be done by the [DeviceNet Registration Page](https://nac.itd.uts.edu.au/guest/game_console_registration.php) but the standard DeviceNet which this services does not reach to the Harry Heath room.

Fortunately DeviceNetNIVC is available in the Harry Heath room which is what we have been using to connect our existing printers to the internet, however this is a more advanced process that requires an exec to contact IT to connect any new printers to the network rather than being able to do it ourselves

Once authorised, a connection can be established on the UI of Bambu Labs printers, or by making an SSH connection to the printer controller and modifying wifi settings over the command line. For Debian based distributions you should be looking for the `wpa_supplicant.conf` file.
You will also need the [DeviceNetNIVC Password😺](https://discord.com/channels/1038007666032787476/1079986034034606130/1394868347627241502)

![[Pasted image 20250911150728.png]]

## Tailscale
Tailscale is a mesh VPN service, essentially it allows us to create a virtual network such that we can act as if we are on the same network as the 3D printers even when we aren't.
While it is more complex to use than the tunnels which we'll talk about in the next section, It's a good backup in case anything happens to the tunnels.
### Setting Up Tailscale (on a Client)
In order to setup Tailscale on a client (such as your personal computer) you'll need to [download Tailscale](https://tailscale.com/download) and login with the [[Technician Google Account|fabsoc technician account]]. This will connect your device to the network (aka Tailnet) as if you are there with the printers in person!
### Setting up Tailscale (on a Printer)
To setup Tailscale on a printer you'll need access to the server device that is managing the printer. This is usually a Raspberry Pi connected to the printer. You'll need access to the command line of the device either by attaching a display and keyboard to the Pi, or SSH into the device via an ethernet cable (if you have that setup)

Once you're in, install Tailscale via the command line:
```
curl -fsSL https://tailscale.com/install.sh | sh
```
and then type
```
sudo tailscale up
```
you will be provided a link to login with, open this link up on another device and login with the [[Technician Google Account|technician account]]
The printer should now be connected to the Tailnet!
## Cloudflare Tunnels
A more convenient method to access the printers can be Cloudflare tunnels! These allow us to access the printer interfaces over the world wide web, provided you have the FabsSoc login.
### Using the Tunnels
Currently we have two tunnels setup for the Endermixer. 
- https://endermixer.tabbycat.dev provides access to the Octoprint instance for the printer and will work as long as you are inside Australia (You still need the [Endermixer login😺](https://discord.com/channels/1038007666032787476/1079986034034606130/1378361883505066014)!)
- https://endermixerssh.tabbycat.dev provides a web SSH client for the raspberry pi connected to the Endermixer. To use it you will need to provide the [[Technician Google Account]] email to receive a login code, then the SSH login can be found in the technician channel: [Technician Link😺](https://discord.com/channels/1038007666032787476/1215834349065469992/1406124743366672435)

> [!Info]- Note on Creating and Managing Tunnels
> Currently the tunnels are managed by Tabby with their personal domain https://tabbycat.dev. Currently this guide doesn't cover creating tunnels since that would require logging into Tabby's personal account but if/when FabSoc acquires its own domain, I will make sure that section is added :3 - Tabby 