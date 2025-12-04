# 🧠 RL-Swarm (Private Setup)
  
#### Thanks to **arcxteam** for the base setup references.

---

## 🧠 Recommended Models

Models (CodeZero):
   - **Qwen/Qwen2.5-Coder-0.5B-Instruct** 
   - **Qwen/Qwen2.5-Coder-1.5B-Instruct**

## ⚙️ Installation Setup

### 1. Update System Packages
```bash
apt update && apt upgrade -y && \
apt install screen curl ufw nload tree iptables git wget lz4 jq make gcc nano automake autoconf \
htop tmux libgbm1 protobuf-compiler python3 python3-pip python3-venv python3-dev python3-setuptools \
tar clang nethogs ncdu unzip build-essential pkg-config libssl-dev libleveldb-dev \
speedtest-cli ca-certificates libffi-dev libsqlite3-dev -y
```

---

### 2. Install Node.js, NPM, Yarn, and PM2
```bash
source <(wget -qO- https://raw.githubusercontent.com/arcxteam/w-ai-wombo/main/nodejs.sh)
```

---

### 3. Install Cloudflared Tunnel
```bash
wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
dpkg -i cloudflared-linux-amd64.deb || apt-get install -f -y
```

---

### 4 INSTALL DOCKER COMPOSE (FOR CPU ONLY, SKIP IF YOU RUN WITH GPU)
```bash
curl -sSL https://raw.githubusercontent.com/arcxteam/succinct-prover/refs/heads/main/docker.sh | bash
```

---

### 5 Clone Repository
```bash
git clone https://github.com/arcxteam/rl-swarm.git && cd rl-swarm
```

---

### 6 Create Screen Session
```bash
screen -S gensyn
cd rl-swarm
```

---

### 7. RUN FOR GPU
```bash
python3 -m venv .venv
source .venv/bin/activate
# If that doesn't work, try:
. .venv/bin/activate
```
```bash
./run_rl_swarm.sh
```

---

### 8. FOR CPU ONLY
```bash
docker compose run --rm --build -Pit --user 0:0 swarm-cpu
```
---

## DETACH SCREEN
`CTRL A+D`

## 🔑 Login (Tunnel Access)
open the tunnel for login:
```bash
cloudflared tunnel --url http://localhost:3000
```
you will see your link, for example : `https://randomstring.trycloudflare.com`

Then open the provided URL in your browser to complete authentication.

---

## After login, Attach Screen
```bash
screen -r gensyn
```

## you will see prompt : 
`Push Model to Huggingface (y/n)` press N
----
`choose model:` (Choose model below)
----
## Models (CodeZero):
   - **Qwen/Qwen2.5-Coder-0.5B-Instruct**
   - **Qwen/Qwen2.5-Coder-1.5B-Instruct**
---

## 🧾 Notes
- This setup guide is for **private use and internal testing only**.  
- Credit to the original authors of RL Swarm and the GenRL framework.  
- Base installation references: **arcxteam**

---

**© 2025 CHATGPT — Private Node Documentation**
