# hosts
 block adware,... hosts
 
 
##Windows users

In Windows 10 the hosts file is located at c:\Windows\System32\Drivers\etc\hosts.

Right click on Notepad in your start menu and select “Run as Administrator”.

 This is crucial to ensure you can make the required changes to the file.

Now click File > Open and browse to : c:\Windows\System32\Drivers\etc\hosts. 
If you can’t view any of the listed directories you will need to configure Windows to show your hidden program 

or System Files as per the guide here.

Add a line to the bottom of the file the following lines, replacing IP_ADDRESS with the IP Address you 

took from the Hosting Control Panel and DOMAIN_NAME with your domain:

```
	IP_ADDRESS DOMAIN_NAME www.DOMAIN_NAME
```
For example:

```
	141.0.161.101 nublue.co.uk www.nublue.co.uk
```
You’ll now need to save the file and you’re done. You should be able to visit your site and view it as it 

appears on the new IP address. You may need to refresh your browser cache to ensure you’re seeing the new version of the site.

You can always test that you’re seeing the site on the IP you wanted by pinging your 

domain or by browsing to https://your-domain-name.com:8443. This will open up the Plesk control panel

 for your site and will show Nublue branding if you’re seeing a version of the site hosted with us.

 You can also see the hostname of the server in the name of the tab you’ve opened.

 This can be very useful in confirming that you’re looking at the correct version of the site, 
 
 especially if both the old and new version of the site are hosted with Nublue.
 
 ##UBUNTU users
 
 Now that you know what the syntax is for each line in the hosts file, we can now show you how to edit it.

On Ubuntu, the hosts file is located within the “/etc/” directory, specifically at “/etc/hosts“.

These steps for editing the hosts file should work on all versions of Ubuntu, including 20.04, 18.04, and 16.04.

1. Within the terminal, we can begin editing the hosts file by using the following command.

For our guide, we will edit this file using the nano text editor as it’s one of the most straightforward editors to use.
```
sudo nano /etc/hosts
```

You may be prompted to enter the password for your account to confirm its elevation to the super user.

2. You should now see the contents of the hosts file on your Ubuntu system.

Within this, you will see some default entries, such as localhost being assigned to the loopback address.

Additionally, you will also see your Ubuntu device’s hostname pointed at the loopback address.
```
127.0.0.1       localhost
127.0.1.1       pimylifeup

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```
3. Adding a new entry to the hosts file on Ubuntu is incredibly simple.

Referring to our syntax section earlier, we know that we need to add an IP address and a hostname.

For this example, let us point the hostname “helloworld“, to the IP address “192.168.0.101“.
```
192.168.0.193 helloworld
```

4. With your new entry, your Ubuntu hosts file should end up looking a bit like what we have below.
```
127.0.0.1       localhost
127.0.1.1       pimylifeup

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters

192.168.0.193 helloworld
```
You can see that we have placed our new example hosts entry to the bottom of the file.

5. You can now save and quit out of the host file.

If you are using nano, you can quit and save by pressing CTRL + X, then Y

6. The easiest way to check if you have configured your hosts file correctly is to ping the new hostname.

For our example, we will use the ping command to see what IP address is being returned for the hostname.
```
ping helloworld
```

7. From this command, you should see your Ubuntu device’s IP address is trying to connect to.

Additionally, if it is a device that accepts pings, you should start getting responses.
```
PING helloworld (192.168.0.193) 56(84) bytes of data.
64 bytes from helloworld (192.168.0.193): icmp_seq=1 ttl=63 time=0.477 ms
64 bytes from helloworld (192.168.0.193): icmp_seq=2 ttl=63 time=0.648 ms
```

In our case, you can see that our hostname, “helloworld” is successfully being routed to the IP we specified.

##Mac users

If you’re on a Mac, the changes you’ll need to make to your hosts file are identical but the process for editing

 the file is different.

You can use the Terminal application to edit your hosts file. To do this, open up Finder 

then Applications > Utilities > Terminal.

From here you can use the following command to edit your hosts file:

sudo nano /etc/hosts

You will have to supply your admin password for the Mac but you should be able to make any necessary amendments

 to the hosts file. When you’re done, use Ctrl + O (followed by Enter) to save the file and then Ctrl + X to exit.