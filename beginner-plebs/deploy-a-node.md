# Deploy a Node

There's several newbie options for getting a Lightning node set up and running.

* [Umbrel](https://getumbrel.com/) is a newbie-friendly package that runs on Raspberry Pi v4+
  * [BTC SESSIONS](https://youtu.be/fppmhqjqh2E) has a good video walkthrough for getting started with Raspberry Pi and Umbrel
* [RaspbiBlitz](https://github.com/rootzoll/raspiblitz) is another option for Raspberry Pi
* [Start9](https://start9.com/) is an all-in-one option that includes the necessary hardware
* [myNode](https://www.mynodebtc.com/) is another all-in-one with hardware
* [RaspiBolt](https://stadicus.github.io/RaspiBolt/) has some good information on how to set up the necessary services manually

#### CheeseRobot ₿

A Telegram bot that will allow you to join and interact with the PLEBNET.

You'll want to send a message to `@cheeserobot` to claim and add your node. Start with `/claim` and follow the instructions to get add your node id. Then, in the PLEBNET channel, use `/id@cheeserobot` to get yourself added to the graph.

To claim your node: 

1. go to @cheeserobot \(click on the name\)
2. go to RTL and copy your nodeID pubkey
3. type `/claim` your-nodeid
4. you will receive a message to be signed, copy it
5. then sign that message using RTL - sign/verify
6. copy the signature
7. then go back to bot and type `/claim <nodeid> <signature>`
8. come to the group and type `/node` 
9. Done 🎉

### Let's Get Personal

#### How to Set an Alias and Color for Your Node

Personalizing your node makes it easier for your node to be identified by others. You can give it a name and a color that shows up when your node is viewed using external applications, such as [1ml](https://1ml.com/) and [graph.kycjelly.com](http://graph.kycjelly.com/).

In order to do this, you will need to access your node via the command line terminal using SSH. If you're using Umbrel/LND, use [these instructions](https://lightningwiki.net/index.php/Setting_alias_and_color_for_Umbrel).

If you're familiar with the Linux command line, you'll find this step very simple. [You can view a cheat sheet of common Linux commands here](https://www.guru99.com/linux-commands-cheat-sheet.html).

![Image](https://i.imgur.com/tElum7G.jpg)

Important note: Whenever you update your node's software, you will need to reset these settings, so you should take note of the these settings for reference. \(Do not overwrite the new lnd.conf with your old version, just update those specific lines.\)

