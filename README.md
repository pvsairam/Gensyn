# Gensyn Testnet (Simplified Guide)

![image](https://github.com/user-attachments/assets/9a714d4c-645d-49b3-a3ce-c2a3095058cc)

| Component     | Minimum Requirement        |
|---------------|----------------------------|
| **CPU**       | arm64 / amd64              |
| **RAM**       | 16+ GB (20+ GB preferred)  |
| **GPU**       | RTX 3090 / 4090 / A100 / H100 (CUDA) |
| **Python**    | Version 3.10+ (Mac may need upgrade) |
| **Storage**   | SSD with free space (x+ GB) |
| **Internet**  | 100 Mbps (1 Gbps+ better)  |

---

## Gensyn Project Links
- Twitter: [@gensynai](https://x.com/gensynai)  
- Discord: [Join here](https://discord.com/invite/bgyDTy39jZ)
---

## 1. Update Server

```bash
sudo apt update -y && sudo apt upgrade -y
```

---

## 2. Install Dependencies

```bash
sudo apt install -y htop curl git wget make unzip jq tmux screen python3 python3-venv python3-pip lz4 build-essential libssl-dev pkg-config ncdu yarn
```

---

## 3. Install Node.js (NVM)

```bash
curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash
source ~/.bashrc
nvm install --lts
```

---

## 4. HuggingFace Setup

- Create account: [huggingface.co](https://huggingface.co/)
- Generate an access token (with **write** access)

![image](https://github.com/user-attachments/assets/dc54f075-915c-438c-a3b7-9c11b55d7c8f)

---

## 5. Clone RL-Swarm Repo

```bash
git clone https://github.com/gensyn-ai/rl-swarm.git
cd rl-swarm
```

---

## 6. Start a Screen Session

```bash
screen -S gensynrlswarm
```

---

## 7. Run Swarm Script

```bash
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```

> - Type `Y` and press Enter when prompted  
> - Open the generated link in browser  
> - Login (Google / Email)  
> - Paste your HuggingFace token

> Done? Press `CTRL + A`, then `D` to detach

---

## .pem File Location

> Save this file:  
> `/root/rl-swarm/swarm.pem`

---

## Optional: NGROK for OTP Login

- Register at [ngrok.com](https://ngrok.com/)
- Get your AuthToken

Install:

```bash
# For x86
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
tar -xvzf ngrok-v3-stable-linux-amd64.tgz
sudo mv ngrok /usr/local/bin/

# For ARM64
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-arm.tgz
tar -xvzf ngrok-v3-stable-linux-arm.tgz
sudo mv ngrok /usr/local/bin/
```

Run:

```bash
screen -S ngrok
ngrok http 3000
```

Click the generated link in your terminal.

---
