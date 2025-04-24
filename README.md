# ✨ No-Brainer XION Mainnet Node Setup (Using Docker Compose)

This is the **fastest and cleanest way** to run a XION mainnet node using Docker Compose. No need to manually configure anything — just clone, build, and run.

---

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

## 🐳 Step 3: Run the Node with Docker Compose

# Clone the repo
git clone https://github.com/web3dopamine/xion-docker-compose.git
cd xion-docker-compose

---

## ▶️ Step 4: Run the Node with Docker Compose

# Start the node
docker-compose up -d


# View logs
docker logs -f xiond-mainnet
---



