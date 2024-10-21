# Volara-Miner
This miner collects our X timeline tweets and generates a transaction on Vana Network (Moksha) to earn points in the dashboard

## Credentials we need
1. X username and password, for access to the Twitter API (Better to be a secondary X account)
2. Google OAUTH, for storing your mined X data in Google Drive
3. Metamask wallet privatekey with funded faucet on Moksha Testnet. [Faucet Link](https://faucet.vana.org/moksha)

## Install Docker
```
# Docker
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo chmod +x /usr/local/bin/docker-compose

# Docker version check
docker --version
```

## Start mining
1. Open Screen
```
screen -S volara
```

2. Replace your metamask private key with `PVKEY`
```
docker pull volara/miner
export VANA_PRIVATE_KEY=PVKEY
docker run -it -e VANA_PRIVATE_KEY=${VANA_PRIVATE_KEY} volara/miner
```

3. Copy the link, Open it in browser, Login your gmail, Copy the given code and paste it in terminal

![Screenshot_442](https://github.com/user-attachments/assets/a7eea536-cc75-47d3-88c0-64799192d0fa)

![Screenshot_443](https://github.com/user-attachments/assets/0a2e19ed-f621-42db-9732-58017703e3be)

4. Fill your X username and password (I removed 2FA for X)

![Screenshot_439](https://github.com/user-attachments/assets/03411043-fcf6-4ba9-82fb-72f17783e85b)

5. Mining started

![Screenshot_440](https://github.com/user-attachments/assets/ec6d6d71-f5ba-4f9b-b4d1-a80ceb57cfed)

* To minimize screen: `Ctrl + A + D`
* To return screen: `screen -r volara`

## Check Miner Points
After a while, You will see your points updating in [Volara Dashboard](https://volara.xyz/)

![image](https://github.com/user-attachments/assets/a837f934-68cc-4a23-a1bc-1162986287b9)

