# Setup Guide

Purchase a VPS. Recommended 5eu/month Contabo server (Up to 30 Masternodes per VPS) Link: https://contabo.com/?show=vps
Download MobaXterm https://mobaxterm.mobatek.net/download-home-edition.html
Start up your VPS in MobaXterm. Use SHH Session and log in using the login information Contabo sent you.

Once connected to VPS:
Enable IPv6 using the following command: <br>
`enable_ipv6` <br>
Then restart ur VPS using: <br>
`sudo reboot`

Once restarted and reconnected to the VPS:
Copy paste the following: <br>
`curl -sL https://raw.githubusercontent.com/neo3587/dupmn/master/dupmn_install.sh | sudo -E bash -`
Make a 50gb swap file copy and paste: <br>
`dupmn swapfile 50000`

When done enabling IPv6 and added the swap file you can enter the following line: <br>
`bash <(curl -Ls https://raw.githubusercontent.com/CowsGoWuff/GenesisX30MN/master/30MNScript)`

Follow the instructions and install up to 1 masternodes. (I'll explain how to add more later)
When the instalation is finished it you will get an output what looks like this: [output_txid] [output_index]
xgs01 [2a02:c212:2031:8066::1:3c02]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 [output_txid] [output_index] 

Open the wallet on your local desktop. (Your main pc where you want to store your coins on)
If you don't have one yet you can download it here: https://github.com/genesis-x/genesis-x/releases

Click on tools and open Masternode Configuration File. Picture example: https://gyazo.com/9d85719f03d690fcea3b3d735a99b12c

Add the outputs from the VPS to the file. Picture example: https://gyazo.com/09c313d0acc3015e53c76120811855b8

Make sure the wallet has coins on it. Each masternode requires 5000 coins.
Open the receive tab and add adresses for the masternodes. 
Picure example: https://gyazo.com/b1bee654e7982b88d54f9154978b8b78

Open the send tab and enter the adress for each masternode and enter 5000 coins as amount. (add recipient to add more than 1 adress)
Picture example: https://gyazo.com/f9dc14c1262ca5a4c4718a86a5efcc4f

Click send and wait till the coins are available again.

Click on tools and open debug console.

Type: "masternode outputs" in the debug console. Picture example: https://gyazo.com/41ea6e42a9f7264d392cd5a647ef6b3e

Add the txid and outputidx to the masternode config file. Picture example : https://gyazo.com/0ce4d2adee3775ee6e462472f1899101

Save the masternode configuration file and restart the wallet.

Open the debug console once the wallet is restarted and type: <br>
`startmasternode alias false xgs01`

You should see a line that says masternode succesfully started.

Congrats you now started 1 masternode! :D

## Adding Additional Masternodes

Open your masternode configuration file.
Add the amount of masternodes you want to add.
Enter the IPv6 adresses you added to the vps.
Open the debug console and type: masternode genkey
Generate a masternode key for each masternode.
Add the [output_txid] [output_index] to the masternode config file. 

Once added all this information the masternode configuration file should look something like this:
`Masternode config file
Format: alias IP:port masternodeprivkey collateral_output_txid collateral_output_index
Example: mn1 127.0.0.2:5555 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0

xgs01 [2a02:c212:2031:8066::1:3c02]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 1
xgs02 [2a02:c212:2031:8066::1:3c03]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 0
xgs03 [2a02:c212:2031:8066::1:3c04]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 1
xgs04 [2a02:c212:2031:8066::1:3c05]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 0
xgs05 [2a02:c212:2031:8066::1:3c06]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 1
xgs06 [2a02:c212:2031:8066::1:3c07]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 0
xgs07 [2a02:c212:2031:8066::1:3c08]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 1
xgs08 [2a02:c212:2031:8066::1:3c09]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 0
xgs09 [2a02:c212:2031:8066::1:3c0a]:5555 87AYbDY3jUHhXF42gesfsd6EJw4Jt4y2sdsdjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 1
xgs10 [2a02:c212:2031:8066::1:3c0b]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 0
xgs11 [2a02:c212:2031:8066::1:3c0c]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 1
xgs12 [2a02:c212:2031:8066::1:3c0d]:5555 87AYbDY3jUHhXF42gesfsd6EJw4JtCAFHY5CjkHRAPLMoWsm485 2fa04d1e20f95f9ed1cce1e6dfe9b1577b5ca1db0b3096dd66732d2eb8b8dbe1 0`
etc etc etc

Next step is to open your VPS in MobaXterm.

Load script: <br>
`bash <(curl -Ls https://raw.githubusercontent.com/CowsGoWuff/GenesisX30MN/master/30MNScript)`

Choose option 2 - Install or add masternodes

Enter the total amount of masternodes you want

Wait for the program to add the masternodes

The script doesnt add any masternode keys or IP adresses above 12 masternodes 
so we have to add them manually:

Go to /home/genesisx13/.genesisx/ and click on genesisx.conf. Picture example: https://gyazo.com/8c2ab6f1e09d8f12c7819778e7157c34

Enter the masternode key and ipv6 adress in the genesisxconf. File Picture example: https://gyazo.com/1442f952b1502ef51d18f0fd0b6cefbe

Do this to every masternode that you would like to add. Example:

Masternode 14 = /home/genesisx14/.genesisx/ <br>
Masternode 15 = /home/genesisx15/.genesisx/ <br>
etc

Once you are done editing/checking all masternode files you can start the masternodes by running the script again: <br>
`bash <(curl -Ls https://raw.githubusercontent.com/CowsGoWuff/GenesisX30MN/master/30MNScript)`

Select option 1 - My masternode status

When the program asks if you want to start the masternode, enter: Y 

Do this for all masternodes

Go to your desktop wallet and click on the Masternode tab. Click "Start all"

If you have other masternodes running already you can alternatively go to the debug console and enter: <br> 
`startmasternode alias false "alias"`
"alias" is the name of the masternode you want to start. etc. xgs13

Repeat this for each masternode you would like to start.

Now you know how to start running your own masternodes :D
I hope this guide helped you !

Feel free to send some coins as gratitude to me as thanks for writing this guide :^)
XGS Wallet adress: GMJe2sANzaFCQgqhEfpPyb16xxechBr6Qp
BTC Wallet adress: 3BajGLbwm79mvL2FSHiXiVqh9fRySWuYNB

The script work was created by SBurns of the Null Entry Project
#And possible follow/fork from https://github.com/sburns1369/
#If anyone recycles please leave credit to the author somewhere
#As well as the donation address for the “Buy the poor guy a red bull”
#BTC address: 32FzghE1yUZRdDmCkj3bJ6vJyXxUVPKY93
#LTC address: MUdDdVr4Az1dVw47uC4srJ31Ksi5SNkC7H
