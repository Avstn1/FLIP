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

### 🏠 Housing System

**Story Start:**  
You've just been kicked out of your parents' house and now live under a bridge with only a sleeping bag.

**Progression:**
1. **Bridge Encampment (Starting Area)**
   - No storage
   - Only carry a few items
   - Sleeping bag "bed"

2. **Condo Apartment (Mid-game)**
   - Unlockable after earning enough money
   - Has indoor room for storage
   - You must buy physical `StorageBox` items to store goods

3. **House / Mansion (Late-game)**
   - Increased storage space
   - Aesthetic upgrades
   - May unlock exclusive buyers or markets

**Classes:**
- `HousingManager`
- `PlayerHousing`
- `StorageBox`
- `StorageManager`
- `SleepSystem` *(optional)*

**Storage Types:**
- Sleeping bag stash (limited slots)
- Storage box (upgradeable size)
- Closet
- Storage Room

---

### 💭 Debatable Systems
**Optional Classes:**
- `PlayerNeedsSystem`  
  (Handles hunger, thirst, sleep, health, etc.)

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
  (Represents shelves, boxes, closets, etc.)
- `StorageBox`  
  (Physical item you buy and place)
- `StorageRoomAccess`  
  (Unlocked via housing upgrade)

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
  - `HousingUI`

## 🕐 Time System
- `TimeManager`  
  (Delivery timing, sales refreshes, event triggers)

### 🌅 Day/Night Cycle

**Core Classes:**
- `TimeManager`  
  Manages accelerated in-game time
- `ClockUI`  
  Shows current time on HUD
- `LightingManager`  
  Adjusts environment lighting (sunlight, moonlight)
- `WorldEventScheduler`  
  Triggers events based on time (store hours, NPC schedules)

**Example Time Phases:**

| Time  | Phase        | Effects                                  |
|-------|--------------|------------------------------------------|
| 6:00  | Dawn         | Warm ambient lighting starts             |
| 9:00  | Morning      | NPCs spawn, shops open                   |
| 12:00 | Midday       | Brightest sunlight                       |
| 18:00 | Evening      | Sunset visuals, shops begin to close     |
| 21:00 | Night        | Late events, special characters appear   |
| 0:00  | Late Night   | Fewer NPCs, risk events like theft       |

**Features:**
- Event cutoffs (deliveries after 5PM arrive next day)
- Late-night flipping or night market bonuses
- Optional fatigue system with `SleepSystem`
- Dynamic lighting via gradients or directional rotation

**Stretch Goals:**
- Seasons & weather
- Energy boosters for extended awake time
- Alarms, timers, and event notifications

**Testing Commands:**
- `T` key: Advance 1 hour  
- `Ctrl + T`: Jump to night  
- Console: `SetTime(hour, minute)`

---

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

### 🏠 Housing & Storage
- `HousingManager`
- `PlayerHousing`
- `StorageManager`
- `StorageBox`
- `SleepSystem` *(optional)*

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
