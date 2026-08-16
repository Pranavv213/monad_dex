
---

# 🌐 Monad Cyber-DEX AI Agent

An autonomous, natural language-driven Decentralized Exchange (DEX) interface built on the **Monad Testnet**. This project bridges the gap between complex Web3 transactions and natural human conversation by pairing **Gemini 2.0 Flash** with **Ethers.js v6** and real-time data visualization.

---

## 🎯 What Is This Project All About?

### 1. The Core Idea

Executing transactions on a Decentralized Exchange (DEX) usually requires manual interaction across multiple UI components: navigating input fields, switching tabs, selecting tokens, configuring slippage, approving ERC-20 allowances, and confirming multi-step transactions.

This project introduces a **"Command & Observe" AI Terminal**:

* **Command:** Users interact using natural, everyday English (e.g., *"Swap 5 of Token A to Token B"* or *"Check pool reserves"*).
* **Observe:** An integrated, dynamic **Chart.js** interface streams a continuous live ticker while idle and locks directly onto real-time, on-chain pool balances the moment an operation completes.

### 2. Key Objectives

* **Zero UI Friction:** Replaces repetitive manual inputs with natural language processing via Gemini 2.0 Flash tool-calling.
* **Automated Web3 Pipeline:** Handles token decimals, ERC-20 `approve` calls, and contract execution in a single automated workflow.
* **Visual On-Chain Feedback:** Features a live, cyberpunk-styled chart that transitions from idle simulation to precise on-chain reserve plotting following every swap or liquidity update.
* **Lightweight & Portable:** Built entirely as a single-file Web interface (`index.html`) using CDNs—requiring zero build tools, node modules, or complex setup.

---

## 🚀 Key Features

* **🤖 Intent-Driven Web3 Agent:** Leverages Gemini 2.0 Flash function-calling to detect parameters (token addresses, amounts) and trigger contract methods directly.
* **📊 Live Dynamic Reserve Visualizer:**
* **Idle Mode:** Animates a dynamic, real-time "zig-zag" streaming line while awaiting input.
* **On-Chain Sync:** Instantly syncs and plots real reserve balances on-chain when a swap, liquidity addition, or reserve query occurs.


* **🔄 Automated ERC-20 Approvals:** Detects token decimals and manages `approve` transactions (`MaxUint256`) behind the scenes before executing router functions.
* **⚡ Monad Testnet Native:** Configured out-of-the-box for high-throughput execution on the Monad DEX router contract (`0x01D54E386b8cfBfFf48A0667cA1885818F761552`).
* **🎨 Cyberpunk Aesthetic:** Custom Tailwind CSS theme featuring glowing neon accents, glassmorphic containers, and a terminal message log.

---

## 🧩 Supported Natural Language Commands

| Action | What the User Says | What the AI Agent Does |
| --- | --- | --- |
| **Add Liquidity** | *"Add liquidity with 10 of 0x111... and 20 of 0x222..."* | Approves both tokens $\rightarrow$ calls `addLiquidity()` $\rightarrow$ Updates live chart reserves |
| **Swap Tokens** | *"Swap 5 of 0x111... to 0x222..."* | Approves input token $\rightarrow$ calls `swap()` $\rightarrow$ Updates live chart reserves |
| **Query Reserves** | *"Get reserves for 0x111... and 0x222..."* | Calls `getReserves()` read function $\rightarrow$ Plots exact pool state on live chart |

---

## 🏗️ System Architecture

```
                 ┌─────────────────────────┐
                 │    User Natural Prompt   │
                 └────────────┬────────────┘
                              │
                              ▼
                 ┌─────────────────────────┐
                 │  Gemini 2.0 Flash API   │
                 │   (Function Extraction) │
                 └────────────┬────────────┘
                              │
                              ▼
┌──────────────────────────────────────────────────────────┐
│                   Ethers.js v6 Execution                 │
│                                                          │
│  1. Check Decimals ──► 2. Approve Token ──► 3. Execute   │
└────────────────────────────┬─────────────────────────────┘
                             │
                             ▼
                 ┌─────────────────────────┐
                 │   Monad Testnet Router  │
                 └────────────┬────────────┘
                              │
                              ▼
                 ┌─────────────────────────┐
                 │   Chart.js Real-time    │
                 │  Reserve Sync & Plot    │
                 └─────────────────────────┘

```

---

## 🛠️ Tech Stack

* **AI Layer:** Google Gemini 3.1 Flash Lite API (Tool / Function Calling)
* **Blockchain Layer:** Ethers.js v6, Web3 Provider (MetaMask), Monad Testnet Router
* **Visualization:** Chart.js
* **Styling:** Tailwind CSS, Google Fonts (Inter & Fira Code)

---

## ⚡ Quick Start

1. **Save the Code:** Save `index.html` locally.
2. **Launch:** Double-click or open `index.html` in any browser.
3. **Connect Wallet:** Click **Connect Wallet** to connect MetaMask (Monad Testnet).
4. **Command:** Type your prompt or click any quick prompt button to execute.
