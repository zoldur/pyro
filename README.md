# PYRO Coin
Shell script to install a [PYRO Coin Masternode](http://pyro.solutions/) on a Linux server running Ubuntu 16.04. Use it on your own risk.

***
## Installation:
```
wget -q https://raw.githubusercontent.com/zoldur/pyro/master/pyro_install.sh
bash pyro_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the **Pyro Coin Desktop Wallet**.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** **PYRO** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Open **Debug Console** and type:
```
startmasternode "alias" "0" "MN1"
```
***

## Usage:
```
pyro-cli mnsync status
pyro-cli getinfo
pyro-cli masternode status
```

Also, if you want to check/start/stop **pyro** , run one of the following commands as **root**:

```
systemctl status pyro #To check the service is running.
systemctl start pyro #To start pyro service.
systemctl stop pyro #To stop pyro service.
systemctl is-enabled pyro #To check whetether pyro service is enabled on boot or not.
```
***

## Donations:  

Any donation is highly appreciated.  

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB

