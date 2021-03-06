# Bravo
Shell script to install a bravo MasterNode on a Linux server running Ubuntu 16.04 x64. Use it on your own risk.<br>
Multiples MN in same VPS not tested<br>
This script was tested on [www.vultr.com](https://www.vultr.com/?ref=7360334) Vps

***
## Installation:
```
wget -q https://raw.githubusercontent.com/devjohn2k/bravoMN/master/install_bravo.sh
chmod 755 install_bravo.sh
./install_bravo.sh
```
***

Follow the steps and save resumen information

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Bravo Wallet
1. Open the **Bravo Desktop Wallet**.
1. Go to RECEIVE and create a New Address: **MN1**
1. Send **10000** **BRV** to **MN1** address.
1. Wait for 15 confirmations.
1. Go to **Tools -> "Debug console - Console"**
1. Type the following command: **masternode outputs**
1. Go to  **Tools -> "Open Masternode Configuration File"**
1. Add the following entry:
```
alias IP:port masternodeprivkey collateral_output_txid collateral_output_index
```
* Alias: **MN1** 
* Address: **VPS_IP:PORT** #see resumen masternode install script
* masternodeprivkey: **Masternode Private Key** #see resumen masternode install script
* collateral_output_txid: **First value from Step 6**
* collateral_output_index:  **Second value from Step 6**
1. Save and close the file.
1. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
1. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. 
1. Select your MN and click **Start Alias** to start it.
1. Alternatively, open **Debug Console** and type:
```
masternode start-alias MN1
```
***

## Usage:
Login with MasterNode User set on install Script
```
brv-cli mnsync status
brv-cli getinfo
brv-cli masternode status #This command will show your masternode status
```

Also, if you want to check/start/stop **bravo** , run one of the following commands as **root**:

```
systemctl status USER.service #To check the service is running.
systemctl start USER.service #To start bravo service.
systemctl stop USER.service #To stop bravo service.
systemctl is-enabled USER.service #To check whetether bravo service is enabled on boot or not.
```
***

## Donations:  

Any donation is highly appreciated.  

**BRAVO**: BME98WH2bZfW9c8KYooyXrmmor7ocQhYzb<br>
**BTC**: 3NHMC1WuAWMrf9xBZFcuseaHx6hfAg66uQ  <br>
**ETH**: 0xf31c809bC7F6A3f592f3ea6565b3C1Fd0Dd776ad<br>
**LTC**: LeRWgzmYA91F9p1Mk3S7u4SNDKDbALujse<br>
