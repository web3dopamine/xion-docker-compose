# 🚀 XION Mainnet Node Setup Guide

This guide walks you through installing `xiond`, configuring the node, and running it with Docker Compose.

---

## 🧱 Step 1: Install Dependencies

Install system packages and Go (version 1.21+):

```bash
sudo apt update
sudo apt install -y build-essential curl git jq

curl -LO https://golang.org/dl/go1.21.6.linux-amd64.tar.gz
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf go1.21.6.linux-amd64.tar.gz
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
source ~/.bashrc
```

---

## 🛠️ Step 2: Build `xiond` from Source

Clone and compile the XION daemon:

```bash
git clone https://github.com/burnt-labs/xion.git
cd xion
git checkout v0.18.0
make install
```

Verify the installation:

```bash
xiond version
```

You should see:

```
0.18.0
```

---

## ⚙️ Step 3: Initialize Your Node

Run this to initialize your node (outside Docker):

```bash
xiond init <YOUR_MONIKER> --chain-id xion-mainnet-1
```

Download the mainnet genesis file:

```bash
curl -L https://snapshots.polkachu.com/genesis/xion/genesis.json > ~/.xiond/config/genesis.json
```


```bash
mkdir -p ./xion
cp -r ~/.xiond ./xion/.xiond
```

---

## 🐳 Step 5: Run the Node with Docker Compose

Create a `docker-compose.yml` in the same directory as this README:

Start the node:

```bash
docker-compose up -d
```

Follow the logs:

```bash
docker logs -f xiond-mainnet
```

---

## ✅ You're All Set

Your node will now sync with the XION mainnet and expose RPC, P2P, gRPC, and other APIs.

🔗 [XION Docs](https://docs.burnt.com/xion)  
🔗 [Polkachu Genesis](https://polkachu.com/tendermint_snapshots/xion)  
🔗 [XION GitHub](https://github.com/burnt-labs/xion)
