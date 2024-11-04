## Colavent Node - Ultimate Guide 

![image](https://github.com/user-attachments/assets/cc20fbe4-7b25-4960-8be8-b0150572368f)

## Requirements

- You must need to buy a VPS for running Covelant Node
- You can buy from : Contabo
- You should buy VPS which is fulfilling all these requirements : 
```bash
Operating System : Ubuntu 22.04
CPU : Minimum of 4 cores
RAM : 4 GB
Storage : SSD or NVMe with at least 50GB of space
```
## Prerequisites
Before you start, ensure you have docker compose installed.
```bash
# Install Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
docker version

# Install Docker-Compose
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)

curl -L "https://github.com/docker/compose/releases/download/"$VER"/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose
docker-compose --version

# Docker Permission to user
sudo groupadd docker
sudo usermod -aG docker $USER
```

## Deployment 
- Step1: 
```bash
wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.22.3.linux-amd64.tar.gz
```

- Step2: 
```bash
echo "" >> ~/.bashrc
echo 'export GOPATH=$HOME/go' >> ~/.bashrc
echo 'export GOROOT=/usr/local/go' >> ~/.bashrc
echo 'export GOBIN=$GOPATH/bin' >> ~/.bashrc
echo 'export PATH=$PATH:/usr/local/go/bin:$GOBIN' >> ~/.bashrc
source ~/.bashrc
```

- Step3: Install Kubo
```bash
wget https://dist.ipfs.tech/kubo/v0.30.0/kubo_v0.30.0_linux-amd64.tar.gz
tar -xvzf kubo_v0.30.0_linux-amd64.tar.gz
```

- Step4:
```bash
cd kubo
sudo bash install.sh
cd
```

- Step5: Git Covalent Repo
```bash
git clone https://github.com/covalenthq/ewm-das
cd ewm-das
```

- Step6: Docker Build
```bash
docker build -t covalent/light-client -f Dockerfile.lc .
```

- Input BURNER `Metamask Private Key` inside Qoutes (do not remove "")

```bash
docker run -d --restart always --name light-client -e PRIVATE_KEY="YOUR_HEX_PRIVATE_KEY" covalent/light-client
```

- Check logs
```bash
docker logs -f light-client
```

## Submit Info and Wait 1 to 2 days ✅
https://docs.google.com/forms/d/e/1FAIpQLSdjxT5NwXX7lBfb_Pdx5T3oWehnaOl__Mg9XnXCr0u-jRPY5w/viewform?usp=send_form

- Join our community https://discord.gg/UPSfxycf
