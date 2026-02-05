# ZPNL (Zero Pain Network Lab)

<div align="center">
  <img src="website/assets/mockup1.png" alt="ZPNL Dashboard Mockup" width="100%" style="border-radius: 10px; box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);">
  <br />
  
  <h1>Orchestrate Your Lab Resources. <br/>Stop The Chaos.</h1>

  <p>
    <strong>ZPNL</strong> is the definitive resource scheduling platform for high-velocity engineering teams. 
    Ditch the spreadsheets and Slack wars. Visualize, book, and manage your physical infrastructure with a tool as modern as the code you write.
  </p>

  <p>
    <a href="#deployment"><strong>Deploy Now</strong></a> · 
    <a href="#features"><strong>Explore Features</strong></a> · 
    <a href="website/index.html"><strong>View Demo Site</strong></a>
  </p>
</div>

---

## 🚀 The Problem: "Is the firewall free?"

In small to mid-sized organizations, managing physical test devices—routers, switches, servers—is often a nightmare of:
*   ❌ **Phantom Bookings:** "I thought Bob was done with it?"
*   ❌ **Spreadsheet Hell:** Outdated, broken shared docs.
*   ❌ **Lost Productivity:** Developers waiting for gear that's actually sitting idle.
*   ❌ **Shadow Usage:** No accountability on who broke the config.

## ✨ The Solution: Uncompromising Clarity

ZPNL eliminates the noise. It provides a **single source of truth** for every cable, rack, and blinking light in your lab. It's not just a scheduler; it's a productivity multiplier.

### Why Teams Love ZPNL

*   **⚡ Blazing Fast Performance:** built on **FastAPI** and **Vite**, interactions are instantaneous. No page reloads, no lag.
*   **🎨 Stunning Visual Design:** A glassmorphism-inspired Dark Mode UI that feels like a premium consumer app, not enterprise gray-ware.
*   **🔒 Local-First Security:** Your topology is your trade secret. ZPNL is designed to be **self-hosted** behind your firewall. No cloud leaks, no external dependencies.
*   **👥 Granular Control:** Role-Based Access Control (RBAC) ensures only Admins can decommission core routers, while Developers have freedom to book what they need.

---

## 🔥 Key Capabilities

### 1. The Visual Timeline
A crystal-clear, 7-day Gantt-style view of every device alongside its availability. Spot gaps instantly.
*   **Drag & Drop (Roadmap)** concept.
*   **Conflict Prevention:** The engine physically prevents overlapping bookings.

### 2. "Quick Book" Workflow
Need a device for the rest of the day?
*   One click using the **"Quick Book"** star button.
*   Smart defaults based on your user profile's favorite device.

### 3. Dynamic Inventory Management
*   **Custom Schemas:** Define platform-specific fields (IOS version, Rack ID, Serial Port) using JSON schemas.
*   **Live Search:** Filter hundreds of devices in milliseconds.

### 4. Lab News Feed
*   Broadcast maintenance windows or critical outages directly in the dashboard.
*   Keep the entire team aligned without mass emails.

---

## 🛡️ Security & Privacy

In an era of cloud-everything, ZPNL stands apart by empowering you to own your infrastructure.
*   **Self-Hosted:** Run it on an internal Ubuntu VM, a Raspberry Pi, or a Docker container.
*   **Data Sovereignty:** All booking data lives in a local `SQLite` database (upgradeable to Postgres).
*   **Zero Telemetry:** We don't track your usage. Your lab is your business.

---

## 🛠️ Deployment Guide

ZPNL is designed to be deployed in minutes, not days.

### Prerequisites
*   **Python:** 3.9+
*   **Node.js:** 18+
*   **OS:** Linux (Ubuntu/Debian recommended), macOS, or Windows (WSL2).

### Step 1: Clone & Configure
```bash
git clone https://github.com/your-org/zpnl.git
cd zpnl
```

### Step 2: Backend Setup (The Engine)
The backend powers the API and database.
```bash
cd backend

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Start the API Server
# Auto-creates the SQLite database on first run
uvicorn app.main:app --host 0.0.0.0 --port 8000
```

### Step 3: Frontend Setup (The Interface)
The frontend connects to your backend API.
```bash
cd frontend

# Install packages
npm install

# Build for production
npm run build

# Preview the production build
npm run preview -- --host
```

### Production Deployment Tips
*   **Reverse Proxy:** We recommend using **Nginx** or **Traefik** in front of the Uvicorn and Vite services.
*   **Process Management:** Use `systemd` or `supervisord` to keep the Python backend running.
*   **Database:** For labs with >50 concurrent users, switch the SQLAlchemy connection string in `backend/app/database.py` to PostgreSQL.

---

## 💼 Enterprise Support

Need custom integrations with LDAP/Active Directory or SSO?
[Contact our Engineering Team](mailto:support@zpnl.lab) for enterprise licensing and support packages.

---
<!-- <p>
  <img width=50% height=50% alt="mockup3" src="https://github.com/user-attachments/assets/f1b3f86e-79aa-4050-9111-b2a0921dccf1" />
 <img width=50% height=50% alt="mockup2" src="https://github.com/user-attachments/assets/224cb60f-4c99-49b8-b33a-2beb160b1956" />
</p>
<p>
<img width=50% height=50% alt="mockup4" src="https://github.com/user-attachments/assets/116cf7b0-9c22-4953-b905-7c6656d08038" />
<img width=50% height=50% alt="mockup5" src="https://github.com/user-attachments/assets/51e2b9a2-917b-4ceb-a344-80d4e73d3dc7" />

</p> -->

<div align="center">
  <small>© 2026 ZPNL Project. Built for Engineers, by Engineers.</small>
</div>
