# 🎮 Game Architecture

This document outlines the base components, systems, and required C# class structures for building the **Hustle & Flip** reselling simulation game.

---

## 📦 Player Component

### 🧍 Customizable Character
**Classes:**
- `PlayerController`
- `CharacterCustomizer`
- `PlayerStats`
- `SkillSystem`
- `ItemAccessibilityManager`

**Customization Options:**
- Limbs
- Head
- Hair
- Skin Color
- Shoes
- Pants
- Watches
- Chains

---

### 📈 LEVELING
**Classes:**
- `PlayerStats`
- `SkillSystem`

Features:
- General player level
- Unlockable skills
- Access to new items or marketplaces

---

### 💭 Debatable Systems
**Optional Classes:**
- `PlayerNeedsSystem`  
  (Handles hunger, thirst, health, etc.)

---

## 🧑‍🤝‍🧑 NPC Component

### 🎭 Randomized Character Models
**Classes:**
- `NPCSpawner`
- `NPCCharacter`
- `NPCDialogueSystem` *(Optional)*

Randomized attributes:
- Limbs
- Head
- Hair
- Skin Color
- Clothing
- Accessories

---

## 💰 Currency

**Classes:**
- `CurrencyManager`

Earn money by:
- Selling items on marketplace
- Door-to-door upselling

---

## 🛍️ Markets

**Classes:**
- `MarketplaceManager`
- `FlipMarketplace`
- `DoorToDoorSystem`
- `Listing`

Market Types:
- Flip Marketplace App (list, wait for buyer)
- Door-to-Door (NPC negotiations)

---

## 📦 Item Storage

**Classes:**
- `InventoryManager`
- `StorageContainer`  
  (Represents shelves, boxes, etc.)

---

## 🎒 Sellable Items

### 🎽 Clothing
- Shirts
- Pants
- Hoodies

### 👟 Shoes
- Yordans (fake brand stand-in)

### 🃏 Card Collectibles
- Spankémon Cards
  - Booster Boxes
  - Rare Cards
- Sports Cards

### 🎁 Item Packaging
- Shoe Boxes
- Card Sleeves
- Display Cases

### 🧢 Wearable Items
- Hats
- Chains
- Rings *(TBD)*

---

### 🧬 Item Structure

**Core Classes:**
- `Item` *(Base Class)*
  - `ClothingItem`
  - `ShoeItem`
  - `CardCollectible`
  - `WearableItem`

**Support Classes:**
- `ItemAttributes`
- `ItemPackaging`

---

### 🔮 Item Attributes

**Classes:**
- `RarityType` *(Enum)*
  - Diamond
  - Gold
  - Silver
  - Bronze

- `StackableItem`

---

## 🧼 Workstations & Utilities

**Base Class:**
- `Workstation`

**Derived Classes:**
- `ShoeCleaningStation`
- `CardCleaningStation`
- `WashingMachine`

**Tool Class:**
- `CleaningTool`  
  (E.g., rag with 10 uses)

---

## 📈 Item Appraisals

**Classes:**
- `AppraisalStation`
- `CardGrader`
- `AppraisalResult`

Mechanics:
- Appraise Spankémon/sports cards
- Determine condition and boost value

---

# 🧠 Additional Systems (To Consider)

## 💾 Save/Load System
- `SaveManager`
- `GameData`

## 🖥️ UI System
- `UIManager`
  - `InventoryUI`
  - `MarketplaceUI`
  - `StatsUI`
  - `DialogUI`

## 🕐 Time System
- `TimeManager`  
  (Delivery timing, sales refreshes, event triggers)

## 🎉 Event System
- `EventManager`
  - Flash sales
  - Hype drops
  - Scams/fraud events

## 🌟 Reputation System
- `ReputationManager`
  - Online seller ratings
  - Access to premium buyers/platforms

## 📦 Delivery System
- `DeliveryManager`
  - Choose delivery options (meetup, courier)
  - Risk of delay/loss

## 📊 Economy System
- `PriceFluctuationManager`
  - Demand/supply curves
  - Regional events affecting prices

## 🏆 Progression/Achievements
- `MilestoneTracker`
  - Tracks first $1K, first hype sale, etc.

---

## 🗂️ Summary of Core Class Families

### 🎮 Gameplay Systems
- `PlayerController`
- `NPCSpawner`, `NPCCharacter`
- `MarketplaceManager`, `DoorToDoorSystem`
- `DeliveryManager`
- `EventManager`, `ReputationManager`
- `SaveManager`, `TimeManager`

### 🧍 Character
- `CharacterCustomizer`
- `PlayerStats`, `SkillSystem`
- `PlayerNeedsSystem` *(optional)*

### 💰 Economy
- `CurrencyManager`
- `PriceFluctuationManager`

### 📦 Items
- `Item` (base class)
- `ItemAttributes`
- `ItemPackaging`
- `RarityType` *(Enum)*

### 🛠️ Workstations
- `Workstation` (base)
- `ShoeCleaningStation`
- `CardCleaningStation`
- `WashingMachine`

### 🧠 Support Systems
- `UIManager`
- `MilestoneTracker`
- `AppraisalStation`, `CardGrader`

---