# Housekeeping

### Maintaining Proper Node Hygiene

#### Keep Your Node Online

When you're running a lightning node, it's important to keep consistent uptime. This is good for you, your peers, and the overall community. Making sure your node stays online improves your reliability, as well as the reliabity of nodes that connect to you. If your node reboots or goes offline repeatedly, your reputation will be negatively impacted, and other peers will choose to route around you. If your node is offline for an extended period of time, you also run the risk of having your open channels force-closed, which can result in losing sats as the channel balance settles on-chain.

#### Set a Static IP Address

One of the most important aspects to keeping your node online is setting a static IP address. Normally, your router assigns IP addresses dynamically to every device on the network. When the router refreshes its IP tables from time to time, some or all of the devices connected to it are reassigned new addresses. Generally, your devices will not alert you when this happens. Some models of wireless printers will display a message on the screen when the IP address changes, but by default, your laptop, smartphone, or node will not inform you when this happens.

The solution for this is to change your router's settings to lock the IP address used by your node. Depending on the type of router you use, this might be referred to as a **manually-assigned IP**, a **reserved IP**, or you may need to simply turn off **automatic IP** assignment. You might have to look in the advanced settings section to find this feature. Once you've set the IP address, you shouldn't have to reboot your node, but if you do, it should retain the same IP address when it comes back up.

![Image](https://i.imgur.com/OwazT9K.jpeg) 

Example of the Reserved IP settings screen on the Google Home app.

