# Tutorial - Mine for blocks with macOS

Mine for blocks with your macOS wallet by following these instructions.

---

### 🔍 Step 1: Open Terminal

- Open **Spotlight Search** (cmd + space) and type:


- Double click on **Terminal** to open it.

---

### 📂 Step 2: Navigate to Downloads Directory

```bash
cd Downloads

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

Enter your sudo password to complete the installation

brew install wget

wget "https://dl.walletbuilders.com/download?customer=7fd7ad0365703844c530ed1b76f8838f9e81a832a1178f1a56&filename=kingpepe-tools-macos.tar.gz" -O kingpepe-tools-macos.tar.gz

tar -xzvf kingpepe-tools-macos.tar.gz

mkdir "$HOME/Library/Application Support/Kingpepe/"

nano "$HOME/Library/Application Support/Kingpepe/kingpepe.conf" -t

Paste the following content into the file

rpcuser=rpc_kingpepe
rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J2
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
p2pport=24028
rpcport=24027
listen=1
server=1
txindex=1
daemon=1
addnode=http://pepe3.org:24027

Save and exit with Ctrl + X, then Y, and Enter

nano mine.sh -t

Paste the following script into the file

#!/bin/bash
SCRIPT_PATH=$(pwd)
echo "Press [CTRL+C] to stop mining."
while :
do
  ./kingpepe-cli generate 1 $(./kingpepe-cli getnewaddress)
done

Save and exit with Ctrl + X, then Y, and Enter

chmod +x mine.sh


./kingpepe-cli createwallet ""

./mine.sh






