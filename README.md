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
