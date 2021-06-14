# Open Some Channels



#### Add Liquidity

Generate a Lightning wallet and add some funds so that you can open channels. Keep in mind that PLEBNET prefers girthy channels, so fund your node accordingly.

#### Find nodes in PLEBNET Telegram group

You'll need to find some other nodes in PLEBNET to open channels with.

You can go to [http://graph.kycjelly.com/](http://graph.kycjelly.com/) to see the current visual graph of nodes, or type `/graph@cheeserobot group` in the PLEBNET chat. `/groupnodes@cheeserobot` will output a list of the 50 most recent members and nodes. You can contact plebs form the graph or list and see if they'd like to open a channel.

You can also just ask in the PLEBNET channel if anyone is interested in opening a channel with you.

#### Keep It Girthy

It's best to have fewer big channels with more sats than it is to have many smaller ones. The recommended minimum channel size is 2 million sats, which would be 1 million per node on the channel.

#### Balanced Channels

The idea is to have balanced channels. This means that there is an equal amount of sats between each node on the channel.

For example, if `Node A` opens a channel with `Node B` for 2m sats, it will start entirely on their end. `Node A` will want to find a way to have 1m sats on each side of the channel.

There are several different ways to accomplish this.

**"Plebmarine Swap"**

**ONLY DO THIS WITH ESTABLISHED AND TRUSTED PLEBNET NODES! IT IS POSSIBLE TO LOSE SATS DOING THIS.**

1. `Node A` opens a channel with X sats
2. `Node B` sends a Lightning invoice for half of the amount X sats that was opened on the channel
3. The `Node A` operator sends the address of their preferred on-chain Bitcoin wallet to the operator of `Node B`
4. The `Node B` operator sends half of the amount X sats of the opened channel to the Bitcoin wallet of the operator of `Node A` from step 3
5. `Node A` pays the Lightning invoice



