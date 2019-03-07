# whobuntu


his blog post announces the release of WhoBuntu v0.0.1 Alpha. WhoBuntu replaces the Whonix workstation. Whobuntu works with Whonix Gateway to establish a Tor connection. The main advantage of WhoBuntu and Whonix are that you are running two different VMs - one for traffic and routing ONLY that has access to the Internet (your Gateway) and one is the machine you use which routes the traffic to the gateway. This prevents a malicious attacker with arbitrary code execution from being able to execute any commands that deanonymize you. It's like a sandbox for Tor. This setup is currently the safest way to run Tor, and yes, it is far safer than Tails (according to the Tor Project).

<h2>How do I get it?<h2>

The following is tested on VirtualBox v6.0, it is highly recommended to use VirtualBox as it is the only supported OS by Whonix. If you choose to use something else YMMV (it probably won't work).

First download the [Whonix Gateway](https://www.whonix.org/wiki/Download) from the Whonix website. Remember we don't need the Workstation, just the gateway. Import the .ova, if prompted choose to reinitialize all MAC addresses, if not it's OK and move on.

Now download this [link](http://) .ova file and import it to VirtualBox. You are now setup to run WhoBuntu.
    
<h2>What now?</h2>

Fire up the whobuntu VM. By default it is protected with LUKS full disk encryption, the password is changeme. Login to the user "user" with the same password.
    
The first step is to [change your LUKS password](https://askubuntu.com/questions/95137/how-to-change-luks-passphrase), ensure this password is strong. Then change your user password with `passwd user` and set it to a strong password.
    

<h2>Features</h2>
    
Of course the main feature is that all traffic transported through Tor. Note that when we say *all traffic*, no matter what application is being used it will run through Tor. Tor only handles TCP connections, so it is likely that any raw UDP packets will be dropped.

Everything Ubuntu Brings with it. Whonix Workstation is based off of Debian 9, which is annoying and not user friendly for many users. WhoBuntu is based off of Ubuntu 18.04 and therefore provides richer repositories, more up to date software, and general ease of use.    

Bundled with the OS is Monero, ZCash, and an Electrum Wallet. ZCash is installed system-wide and can be started with `zcashd`. Monero can be started by finding monerod in the monero folder on the Desktop. Electrum can be started by double clicking the .AppImage file on the desktop. Note that the blockchains need to be downloaded once a wallet is initiated - this could take a while over Tor, so it's recommended to start immediatement.
    
Unnecessary or dangerous daemons disabled by default. Apport, for example, provides usage statistics and a memory snapshot of crashed programs. This could be used to deanonymize you so it has been disabled.
    
<h2>WARNING!!</h2>
    
WhoBuntu is in Alpha and is not recommended for strong anonymity. In particular a more thorough review of all daemons running still has not been done.
    
    
