# egade_order — Advanced Player Order Market System 


![Minecraft Version](https://img.shields.io/badge/Minecraft-26.2%20%7C%201.21.x-brightgreen?style=for-the-badge&logo=minecraft)
![Tested Platform](https://img.shields.io/badge/Tested%20On-Paper%2026.2-blue?style=for-the-badge)
![Java Version](https://img.shields.io/badge/Java-21%20%2F%2026%20%2B-orange?style=for-the-badge&logo=openjdk)
![Economy](https://img.shields.io/badge/Economy-Vault%20API-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-Non--Commercial-red?style=for-the-badge)

(no LICENSE to use) **egade_order** is a modern, high-performance, asynchronous item purchasing and order market plugin built for Minecraft **Paper / Purpur 26.2 & 1.21.x** servers. It enables players to create custom buy-orders for any item, automatically hold deposited funds in an escrow vault, and allow sellers to fulfill orders through an interactive, drag-and-drop delivery chest.

Developed and maintained by **egade369**.

---

##  Tested & Verified Environment

> [!NOTE]
> This plugin has been actively tested and verified on **Paper 26.2** running **Java 26** (paper-26.2-112). It is designed to maintain broad backward and forward compatibility with Paper/Purpur 1.21+ and modern Paper builds.

---

##  Key Features

### 1. 🛒 Player-Driven Order Market
- Players can create public purchase requests (Orders) for any Minecraft item.
- Set custom desired quantities (from 1 up to 100,000 units) and unit prices.
- Live pagination browsing through all available active market orders.

### 2.  100% Scam-Proof Escrow System (Vault Integration)
- When a buyer creates an order, the total required balance (quantity * unit_price) is immediately deducted and safely locked in the order vault.
- Sellers are guaranteed to receive instant payment into their account as soon as items are delivered.
- If an order is cancelled or expires, unfulfilled funds are instantly refunded to the buyer.

### 3.  Smart Drag-and-Drop Delivery Chest
- Sellers simply click on any order to open a 36-slot Delivery Box.
- Place items into the chest and close/exit (ESC or inventory close).
- The plugin automatically scans, verifies matching item types, deposits items into the buyer's order storage, pays the seller instantly, and returns any non-matching or excess items back into the seller's inventory safely.

### 4.  Interactive Storage & Flexible Collection
- When sellers fulfill orders, items are placed in a dedicated virtual storage buffer for the buyer.
- Buyers can collect items directly into their inventory or drop them in front of themselves.
- Built-in take multipliers allow taking **x1, x16, x32, x64**, or **x2,304 (36 full stacks / entire inventory)** in a single click.

### 5.  Multi-Criteria Search & Sorting
- **Real-Time Search:** Search the market or item catalog by item name, material type, or keywords.
- **Sorting Options:**
  -  **Newest First** (Default)
  -  **Oldest First**
  -  **Lowest Price / Unit**
  -  **Highest Price / Unit**
  -  **Name (A - Z)**
  -  **Name (Z - A)**

### 6.  Interactive Chat Tag [order]
- Players with active buy orders can type [order] anywhere in the public chat.
- The tag automatically transforms into a rich, hoverable, and clickable MiniMessage button.
- Clicking the tag instantly opens a filtered view showing only that player's active orders.

### 7.  Configurable Expiration & Cancellation
- Orders feature a configurable lifespan (default: 3 days) to keep market data clean.
- Buyers can cancel active orders at any time as long as all stored items have been collected.

---

##  System Requirements

| Requirement | Minimum / Recommended |
| :--- | :--- |
| **Tested Server** | **Paper 26.2** (Compatible with Paper / Purpur 1.21+) |
| **Java Environment** | **Java 21, Java 25, Java 26+** |
| **Core Dependency** | **Vault** (with any compatible economy provider such as EssentialsX) |
| **Soft Dependency** | **PlaceholderAPI** |

---

##  Installation Guide

1. Ensure your server is running **Paper 26.2 (or Paper 1.21+)** with **Java 21 / 26+**.
2. Download the latest egade_order.jar release.
3. Place egade_order.jar into your server's plugins/ folder.
4. Make sure you have **Vault.jar** and an economy plugin (e.g., **EssentialsX.jar**) installed in plugins/.
5. Restart your server or run your server startup script (
un.bat / 
un.sh).
6. The configuration file and database will be generated automatically at plugins/egade_order/.

---

##  In-Game Commands & Subcommands

All main functionality is available through the /order command:

| Command | Permission | Description |
| :--- | :--- | :--- |
| /order | egade.order.use | Opens the main Order Market graphical interface. |
| /order search <keyword> | egade.order.use | Filters market listings by the specified item or keyword. |
| /order user <player> | egade.order.use | Displays only the active purchase orders created by a specific player. |
| /order resetsearch | egade.order.use | Clears your active search filter and reopens the market. |
| /order setamount <quantity> | egade.order.use | Internal/chat helper to set quantity during order setup. |
| /order setprice <price> | egade.order.use | Internal/chat helper to set unit price during order setup. |



##  Configuration (config.yml)

The default configuration file is located at plugins/egade_order/config.yml:

yaml

##  egade_order - Plugin Configuration


### Chat prefix displayed before all system messages
 prefix: "&8[&6&lOrder&8] "

### Currency symbol used in GUI displays
 currency_symbol: "$"

### Maximum number of active market orders a single player can maintain concurrently
 max_orders_per_player: 5

### Duration (in days) before an unfulfilled order is marked as expired
 order_expire_days: 3

### Whether to broadcast a clickable global announcement when a new order is posted
 broadcast_new_order: true

#
#

## ❓ Frequently Asked Questions (FAQ)

### Q: What versions is this plugin tested on?
**A:** This plugin was tested and confirmed working on **Minecraft / Paper 26.2** running **Java 26**.

### Q: What happens if my inventory is full when collecting items?
**A:** Any items that cannot fit into your inventory will automatically be dropped safely at your feet.

### Q: Can players scam by canceling an order while someone is delivering?
**A:** No. All delivery calculations are performed atomically on inventory closure. If items are accepted, funds are instantly transferred via Vault, and the order progress updates immediately.

### Q: How does the [order] chat tag work?
**A:** When any player who owns active market orders types [order] in public chat, the text is replaced with a styled button [ 📦 Order ]. Other players can click it to view and fulfill their orders directly.



## 📜 License & Terms of Use

This software is released under a **Custom Non-Commercial License**.

- ✅ **Permitted:** Free usage, installation, and modification for personal, private, or non-commercial public Minecraft servers.
- ❌ **Prohibited (Strictly Forbidden):** Selling, reselling, sublicensing, monetizing, or bundling this plugin into commercial packages for monetary gain.

For complete legal terms, please inspect the included [LICENSE](LICENSE) file.

---

*Crafted with passion by **egade369**.*
