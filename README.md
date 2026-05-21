```
██████╗ ██████╗ ██╗   ██╗███╗   ██╗██╗  ██╗    ██████╗  █████╗ ████████╗
██╔══██╗██╔══██╗██║   ██║████╗  ██║██║ ██╔╝    ██╔══██╗██╔══██╗╚══██╔══╝
██║  ██║██████╔╝██║   ██║██╔██╗ ██║█████╔╝     ██████╔╝███████║   ██║   
██║  ██║██╔═══╝ ██║   ██║██║╚██╗██║██╔═██╗     ██╔══██╗██╔══██║   ██║   
██████╔╝██║     ╚██████╔╝██║ ╚████║██║  ██╗    ██║  ██║██║  ██║   ██║   
╚═════╝ ╚═╝      ╚═════╝ ╚═╝  ╚═══╝╚═╝  ╚═╝    ╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   
                                                                          
⚡ REMOTE ADMINISTRATION TOOL | ENTERPRISE-GRADE AGENT MANAGEMENT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

# 🔐 DPUNK RAT

> **D**istributed **Punk** Remote Administration Tool — A high-performance, TypeScript-based Remote Administration framework for enterprise operations.

---

## ✨ Features at a Glance

- **🚀 Blazing Fast** — TypeScript/Node.js server, Go agents, encrypted WebSocket comms
- **🎮 Dual Interface** — Web panel + native Electron/Tauri desktop application
- **🔒 End-to-End Encrypted** — Military-grade encryption for all agent communications
- **🌐 WebRTC Streaming** — Low-latency remote desktop with multiple transport options
- **🔌 Plugin System** — Native Go plugins for custom modules and extensions
- **📊 Multi-Agent Management** — Manage thousands of agents from a single dashboard
- **🐳 Docker Ready** — One-command deployment across Windows, Linux, and macOS
- **🔄 Real-Time Updates** — Live agent metrics, command execution, and event streaming

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    DPUNK RAT ECOSYSTEM                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────────────┐         ┌──────────────────────────────┐ │
│  │  Web Dashboard   │         │  Desktop Application         │ │
│  │  (React/Vue)     │◄────────┤  (Tauri/Electron)          │ │
│  └──────────────────┘         └──────────────────────────────┘ │
│           │                              │                      │
│           └──────────────┬───────────────┘                      │
│                          │                                      │
│                   ┌──────▼──────┐                              │
│                   │ DPUNK Server │ (TypeScript/Node.js)        │
│                   │  (Bun/Node)  │                              │
│                   └──────┬──────┘                              │
│                          │                                      │
│         ┌────────────────┼────────────────┐                    │
│         │                │                │                    │
│    ┌────▼────┐      ┌────▼────┐     ┌────▼────┐              │
│    │  Agent  │      │  Agent  │     │  Agent  │  (Go)        │
│    │ (Win)   │      │ (Linux) │     │ (macOS) │              │
│    └─────────┘      └─────────┘     └─────────┘              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Server:** TypeScript on Node.js/Bun  
**Agents:** Go (cross-platform)  
**Communication:** Encrypted WebSockets + TLS  
**Storage:** Persistent data, audit logs, agent profiles

---

## 🚀 Quick Start (Docker)

The fastest way to get up and running. Choose your platform:

### Windows

```powershell
# 1. Install Docker Desktop
winget install -e --id Docker.DockerDesktop

# 2. Clone the repository
git clone https://github.com/dpunk12/Dpunk-RAT.git
cd Dpunk-RAT

# 3. Start DPUNK RAT
docker compose -f docker-compose.windows.yml up -d

# 4. Open the panel
# Visit: https://localhost:5173
# Default login: admin / admin
```

<details>
<summary>📖 Detailed Windows Setup</summary>

**Step 1: Install Docker Desktop**

Either from the website:
- https://docs.docker.com/desktop/setup/install/windows-install/

Or with winget:

```powershell
winget install -e --id Docker.DockerDesktop
```

Start Docker Desktop once, then verify:

```powershell
docker --version
docker compose version
```

**Step 2: Get the project**

```powershell
git clone https://github.com/dpunk12/Dpunk-RAT.git
cd Dpunk-RAT
```

**Step 3: Start it**

```powershell
docker compose -f docker-compose.windows.yml up -d
```

**Step 4: Open the panel**

```
https://localhost:5173
```

**Step 5: Update later**

```powershell
docker compose -f docker-compose.windows.yml down
docker compose -f docker-compose.windows.yml pull
docker compose -f docker-compose.windows.yml up -d
```

**Step 6: Stop**

```powershell
docker compose -f docker-compose.windows.yml down
```

</details>

---

### Linux (Debian/Ubuntu/Kali)

```bash
# 1. Install Docker
sudo apt update && sudo apt install -y docker.io docker-compose

# 2. Enable Docker service
sudo systemctl start docker
sudo systemctl enable docker

# 3. Clone and start
git clone https://github.com/dpunk12/Dpunk-RAT.git
cd Dpunk-RAT
docker compose up -d

# 4. Access the panel
# Visit: https://localhost:5173 or https://<your-ip>:5173
```

<details>
<summary>📖 Detailed Linux Setup</summary>

**Step 1: Install Docker**

Official docs: https://docs.docker.com/engine/install/debian/

Set up Docker's apt repository:

```bash
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/debian
Suites: $(. /etc/os-release && echo "$VERSION_CODENAME")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
```

Install Docker:

```bash
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Verify:

```bash
sudo systemctl status docker
```

**Step 2: Get the compose file**

```bash
mkdir dpunk-rat && cd dpunk-rat
wget https://raw.githubusercontent.com/dpunk12/Dpunk-RAT/refs/heads/main/docker-compose.yml
```

**Step 3: Start it**

```bash
docker compose up -d
```

The image is pulled automatically from Docker Hub on first run.

**Step 4: Open the panel**

```
https://localhost:5173
or
https://<your-server-ip>:5173
```

**Step 5: Update later**

```bash
docker compose down
docker compose pull
docker compose up -d
```

**Step 6: Stop**

```bash
docker compose down
```

</details>

---

### macOS

```bash
# 1. Install Docker Desktop
brew install --cask docker

# 2. Clone and start
git clone https://github.com/dpunk12/Dpunk-RAT.git
cd Dpunk-RAT
docker compose -f docker-compose.windows.yml up -d

# 3. Open https://localhost:5173
```

<details>
<summary>📖 Detailed macOS Setup</summary>

**Step 1: Install Docker Desktop**

Either from the website:
- https://docs.docker.com/desktop/setup/install/mac-install/

Or with Homebrew:

```bash
brew install --cask docker
```

Start Docker Desktop once, then verify:

```bash
docker --version
docker compose version
```

**Step 2: Get the project**

```bash
git clone https://github.com/dpunk12/Dpunk-RAT.git
cd Dpunk-RAT
```

**Step 3: Start it**

macOS uses the same compose file as Windows:

```bash
docker compose -f docker-compose.windows.yml up -d
```

**Step 4: Open the panel**

```
https://localhost:5173
```

**Step 5: Update later**

```bash
docker compose -f docker-compose.windows.yml down
docker compose -f docker-compose.windows.yml pull
docker compose -f docker-compose.windows.yml up -d
```

**Step 6: Stop**

```bash
docker compose -f docker-compose.windows.yml down
```

</details>

---

## 🛠️ Manual Setup (No Docker)

If you prefer to run without Docker, use the included scripts.

**Prerequisites:**
- Bun (https://bun.sh)
- Go 1.21+ (https://golang.org)

### Windows

Development mode (starts server + client):

```bat
start-dev.bat
```

Production mode (build + run server executable):

```bat
start-prod.bat
```

Build client binaries:

```bat
build-clients.bat
```

### Linux / macOS

Make scripts executable:

```bash
chmod +x start-dev.sh start-dev-server.sh start-dev-client.sh start-prod.sh build-prod-package.sh
```

Development mode:

```bash
./start-dev.sh
```

Only server or only client:

```bash
./start-dev.sh server
./start-dev.sh client
```

Production mode:

```bash
./start-prod.sh
```

---

## 📦 Production Deployment

Build a production-ready package:

**Windows:**

```bat
build-prod-package.bat
```

Output: `release/`

**Linux / macOS:**

```bash
./build-prod-package.sh
```

Output: `release/prod-package/`

---

## 🖥️ Desktop Application

DPUNK RAT includes a native desktop client built with **Tauri 2** (Rust + system webview).

### Features

- Native desktop window with operator connection screen
- Remembers server address across launches
- TLS toggle for HTTP/HTTPS
- Accepts self-signed certificates
- Cross-platform support (Windows, macOS, Linux)
- ~10 MB installer size

### Building the Desktop App

**Prerequisites:**
- Rust (https://rustup.rs)
- Bun
- Platform dependencies (see Tauri docs)

**Quick Start:**

```bash
cd Overlord-Desktop
bun install
bun run start
```

**Build for Distribution:**

```bash
bun run build:win      # Windows NSIS installer
bun run build:mac      # macOS DMG
bun run build:linux    # Linux AppImage
```

---

## 🎥 Remote Desktop & Streaming

The remote viewer supports **three transport modes**:

1. **Canvas (Default)** — H.264/JPEG over WebSocket, decoded to `<canvas>`
   - Works anywhere WebSocket connects
   - Highest latency but most compatible

2. **WebRTC P2P** — Direct browser ↔ agent connection
   - Lowest latency
   - Server relays SDP/ICE candidates only
   - May fail behind strict NATs

3. **WebRTC Relayed** — Agent → MediaMTX → Browser
   - Low latency with fallback
   - Server proxies signaling
   - Authentication maintained

### Enabling WebRTC for Agents

In the builder UI, check the **WebRTC** checkbox before building. This adds the Pion stack (~6 MB).

Or build with the tag:

```bash
go build -tags overlord_webrtc ./cmd/agent
```

---

## 🔌 Plugin System

Extend DPUNK RAT with custom Go plugins. See `plugins/sample-go/` for an example.

### Plugin Files

At the root of the plugin zip:
- `plugin-name-linux-amd64.so`
- `plugin-name-darwin-arm64.dylib`
- `plugin-name-windows-amd64.dll`
- `plugin-name.html` (UI)
- `plugin-name.css` (Styling)
- `plugin-name.js` (Frontend logic)

### Building a Plugin

```bash
cd plugins/sample-go
./build-plugin.sh

# Multiple targets
BUILD_TARGETS="linux-amd64 linux-arm64 darwin-arm64" ./build-plugin.sh

# Windows
build-plugin.bat
```

The script automatically creates a zip file. Place it in `Overlord-Server/plugins`.

### Using Your Plugin

Navigate to: `/plugins/sample?clientId=<CLIENT_ID>`

---

## ⚙️ Configuration

### Default Credentials

On first start:
- **Username:** `admin`
- **Password:** `admin`

Override with environment variables:
```
OVERLORD_USER=myuser
OVERLORD_PASS=mypassword
```

### Port Configuration

Default: **5173** (HTTPS)

Change with:
```
PORT=8443
```

### TLS / HTTPS

DPUNK RAT auto-generates self-signed certificates on first start. For production with Let's Encrypt:

```
OVERLORD_TLS_CERTBOT_ENABLED=true
OVERLORD_TLS_CERTBOT_DOMAIN=your-domain.com
```

---

## 🌐 Advanced Networking

### Reverse Proxy / TLS Offload

If your platform terminates TLS before reaching DPUNK RAT (Render, Caddy, nginx, etc.):

```
OVERLORD_TLS_OFFLOAD=true
OVERLORD_HEALTHCHECK_URL=http://localhost:5173/health
OVERLORD_PUBLISH_HOST=127.0.0.1
OVERLORD_TRUST_PROXY=true
```

### WebRTC Additional Hosts

For operators on different machines:

```bash
OVERLORD_WEBRTC_ADDITIONAL_HOSTS=127.0.0.1,192.168.1.42
docker compose -f docker-compose.windows.yml up -d mediamtx
```

---

## 📊 Dashboard Highlights

- **Real-Time Metrics** — CPU, memory, disk, network for each agent
- **Command Execution** — Run PowerShell, Bash, or custom scripts
- **File Management** — Upload, download, and browse agent file systems
- **Process Management** — View, kill, or manipulate processes
- **Audio Capture** — Stream live audio from target systems
- **Screen Capture** — High-fidelity remote desktop with low latency
- **Log Viewer** — Persistent audit logs and event history

---

## 📚 Documentation Structure

- **README.md** — This file (overview + quick start)
- **Overlord-Server/** — Backend server (TypeScript/Bun)
- **Overlord-Desktop/** — Native desktop client (Tauri 2)
- **client-agent/** — Go agent (Windows/Linux/macOS)
- **plugins/** — Custom plugin examples and templates
- **.github/workflows/** — CI/CD pipelines

---

## 🔗 Useful Links

- **Docker Docs:** https://docs.docker.com
- **Bun:** https://bun.sh
- **Go:** https://golang.org
- **Tauri:** https://tauri.app
- **Node.js:** https://nodejs.org

---

## ⚠️ Legal & Disclaimer

DPUNK RAT is provided **for authorized security testing and enterprise operations only**. Unauthorized access to computer systems is illegal. Users are solely responsible for complying with all applicable laws and regulations.

This tool is designed for:
- ✅ Security professionals and penetration testers
- ✅ IT administrators managing authorized systems
- ✅ Enterprise infrastructure monitoring
- ✅ Educational purposes in controlled environments

Misuse is prohibited and may result in legal consequences.

---

## 🤝 Support & Community

- **Issues:** Report bugs and feature requests on GitHub
- **Discussions:** Community support and best practices
- **Pull Requests:** Contributions welcome (fork + PR)

---

## 📄 License

Licensed under **Apache 2.0**. See `LICENSE` for details.

---

<div align="center">

**⚡ DPUNK RAT — Enterprise Remote Administration, Reimagined ⚡**

*Built for security professionals. Tested in the field.*

</div>
