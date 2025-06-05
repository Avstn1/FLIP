# 🏁 Sprint 1 Planner – Core Gameplay Loop (Week 1)

**Sprint Goal:**  
Build the foundational systems for the player, item handling, and marketplace loop using Unity and C#. The player should be able to buy a basic item and list it for sale.

---

## ✅ Key Objectives

| Task | Description | Priority |
|------|-------------|----------|
| Setup Project | Initialize Unity URP project, setup folders, source control (Git) | 🔥 High |
| Player Controller | Basic movement, interaction raycast | 🔥 High |
| Base Item System | Create base `Item` class and test prefab | 🔥 High |
| Inventory System | Add/remove items, simple UI | 🔥 High |
| Flip Marketplace UI | Minimal UI for listing/viewing item | 🔥 High |
| Sell Item System | Simulate sale after timer or button click | 🔥 High |
| Currency System | Simple money tracker and display | 🔥 High |
| Simple NPC Buyer | Simulate random sale offer | 🟡 Medium |
| Debug HUD | Display money, item name, player state | 🟡 Medium |

---

## 🗂️ Suggested Folder Structure

/Scripts
/Player
/Items
/UI
/Market
/Systems

/Prefabs
/Items
/UI
/Environment

/Scenes
/TestScene

/Art
/UI
/Icons


---

## 🧱 Suggested C# Class Skeletons

- `PlayerController.cs`  
  Basic movement + raycast interaction

- `Item.cs`  
  Base data class for all resellable objects

- `InventoryManager.cs`  
  Stores list of player-owned items

- `MarketplaceManager.cs`  
  Handles UI and logic for listing/selling

- `CurrencyManager.cs`  
  Tracks and updates player money

- `UIInventoryPanel.cs`  
  Visual inventory list

- `UISellPanel.cs`  
  Simple UI for setting price and confirming sale

- `NPCBuyerSimulator.cs`  
  Simulates a buyer after X seconds

---

## 🎮 MVP Gameplay Loop

**Goal:** Allow a player to buy an item and sell it for money.

- [ ] Pick up an item in the world
- [ ] Item gets added to inventory
- [ ] List the item through Flip Marketplace UI
- [ ] Simulate NPC buyer after 5–10s
- [ ] Show money increase and remove item

---

## 📆 Timeline (5-Day Sprint Example)

| Day | Tasks |
|-----|-------|
| Mon | Unity setup, create folders, basic player controller |
| Tue | Implement `Item`, `InventoryManager` |
| Wed | Build UI for inventory and marketplace |
| Thu | Hook up sell system, currency updates |
| Fri | Test full buy/sell loop, polish, bug fix, push to GitHub |

---

## 🎯 Stretch Goals (Optional)

- [ ] Add 2nd item type (e.g. Shoe or Card)
- [ ] Add item condition attribute (New/Used)
- [ ] Add placeholder rarity system
- [ ] Add temporary player HUD for money + inventory count

---

## 🧪 Sprint Review Criteria

- ✅ Player can interact with and acquire items
- ✅ Items appear in inventory
- ✅ Items can be listed for sale via UI
- ✅ Items get sold after a delay
- ✅ Money increases appropriately

---

## 🛠️ Tools Required

- Unity (URP Recommended)
- Git for version control
- Optional: Trello / Notion for task tracking

---
