# Product Requirements Document (PRD)

**Project Name:** Live Music Dopamine Simulator  
**Version:** 1.0  
**Status:** Approved  
**Target Platform:** Desktop-First Web Application  

---

## 1. User Persona & Strategic Intent

* **Target User:** Live music fans seeking the thrill of discovering real artists, securing ticket drops, and purchasing tour merchandise.
* **Core Intent:** Deliver a desktop-first, zero-risk, high-satisfaction "dopamine simulator" that recreates the emotional highs of concert drops, ticket purchases, and merch queues with virtual money, simulated fees, and no real-world financial transaction.

---

## 2. Problem Statement & Solutions

| Real-World Pain Point | Dopamine Simulator Solution |
| :--- | :--- |
| **Ticketing Anxiety & Scalper Bots:** Dynamic surge pricing, instant sell-outs, and checkout errors. | **Simulated Checkout & Guaranteed Access:** Simulated ticket prices, visible virtual fees and tax, timed seat holds, and ticket claiming through the virtual wallet. |
| **Merch Queue Friction:** Long physical lines at venue merch booths where desired sizes and limited items sell out quickly. | **Gamified Tap Queue:** Low-friction crowd-navigation tap game engineered with high win rates so users consistently reach the table. |
| **Financial Stress:** High financial barrier to entry for tickets, fees, and apparel. | **Simulated Economy:** Seeded virtual wallet, preset top-ups, custom top-ups, site-time rewards, and daily deal spins with no real payment processing. |

---

## 3. Feature Architecture & Capabilities

### 3.1 Ticket Intelligence Engine
* **Dynamic Price Drop Alerts:** Simulates real-time price fluctuations across secondary and venue ticket markets, triggering visual price-drop badges.
* **Presale & Drop Tracker:** Interactive calendar counters and notifications alerting users to upcoming fictional tour presales and venue drops.
* **Seat Selection Support:** Venue diagrams, section availability, preview images, and clear per-section pricing help users choose seats before checkout.

### 3.2 Concert & Merch Experience Hub
* **Event-Day Activation Mode:** Dedicated top-level interface mode that activates on show day or when triggered manually by the user.
* **Integrated Artist Audio Experience:** Automatic playback of authentic audio tracks, top hits, and live previews from the selected real-world artist.
* **Interactive Merch Catalog:** Previews of tour-exclusive apparel, accessories, posters, and limited variants with full size selections.
* **Gamified Queue Gateway:** Light crowd-navigation tap mini-game allowing users to move through the venue crowd and access the merch booth.

---

## 4. Data Model & Input Requirements

* **Embedded Artist & Audio Database:** An extensive, self-contained local database containing authentic artist metadata, track titles, album artwork, and audio clips—eliminating external API dependencies.
* **Procedural Concert Generator:** System engine that pre-populates fictional tour dates, virtual venue seat maps, simulated pricing models, and virtual merch catalogs.
* **User Preference Mapping:** Guest and member profiles store local ticket, merch, wallet, and profile history separately.
* **Simulated Wallet Engine:** Tracks virtual funds, starts with a small seeded balance, and supports preset top-ups, custom top-ups, site-time rewards, and deal-wheel bonuses.

---

## 5. End-to-End User Workflows

### Flow 1: Setup & Customization
1. User opens the desktop app and browses the pre-loaded artist database.
2. User selects favorite artists to populate their custom tour schedule.
3. User can add virtual wallet funds through preset amounts, custom amounts, site-time rewards, or the daily deal wheel.

### Flow 2: Ticket Procurement
1. User monitors upcoming show drops and evaluates real-time price-drop indicators.
2. User selects seats using the venue map, section availability, preview images, and prices.
3. User completes a simulated paid checkout with virtual wallet funds and receives a digital ticket stub.

### Flow 3: Concert & Merch Experience (The Dopamine Loop)
1. User observes the locked door state or activates the **Speed Up Time** button to fast-forward to showtime immediately.
2. At showtime, the ticket switches to a ready state until the user clicks **"Enter Concert"**.
3. Upon entering Concert Mode, audio playback begins automatically with real artist tracks.
4. User plays a low-friction crowd-navigation tap game with guaranteed high success rates to reach the merch booth.
5. User selects apparel, chooses sizes, completes instant checkout, and adds items to their persistent digital collection.

---

## 6. System Constraints & Operational Policy

* **Platform Target:** Desktop-first web application optimized for widescreen desktop viewports and browser layouts.
* **Non-Transactional Boundary:** Zero real currency processing, payment gateways, or live e-commerce integrations.
* **Zero API Dependencies:** Fully offline-capable local dataset for media, artist metadata, and store inventory.
* **Positive Game Mechanics:** Queue logic engineered specifically to prevent punishing failure states and maximize user satisfaction.

---

## 7. Interface Requirements & Visual Theme

* **Clean Ticket Marketplace Theme:** Light marketplace pages for browsing and checkout, with darker high-energy surfaces for account entry, concert mode, wallet, deals, and merch moments.
* **Muted Music Accents:** Indigo, emerald, and violet highlights with subtle audio visualizer animations, avoiding harsh neon flashing.
* **Top Header Navigation:** Global header displaying artist search on larger screens, deal wheel access, wallet balance, digital ticket wallet, and profile access.
* **Dashboard & Concert Hub:** Grid-based event layouts, dedicated audio playback controls, **Speed Up Time** trigger, **Enter Concert** action cards, and merch access from saved tickets or the stage.

---

## 8. Technical Constraints & State Persistence

### 8.1 Auto-Save & Full Persistence Across Reloads
All user state—including remaining wallet balance, guest/member account data, secured tickets, purchased merch collection, daily deal state, and active concert door state—is continuously persisted in browser storage (`localStorage` / `IndexedDB`). Page reloads or session restarts restore exact user progress seamlessly.

### 8.2 Technical Architecture
* **Single Page Application (SPA):** Built as a client-side web application operating without backend dependencies.
* **HTML5 Audio API:** Handles local audio clip streaming, track playback controls, and volume synchronization.
* **Clock State Engine:** Centralized simulation clock that tracks event timers, fast-forward multipliers, and transition states.

### 8.3 State Persistence Schema Example
```json
{
  "userWallet": {
    "isUnlimited": false,
    "balance": 25.00,
    "lastSiteTimeRewardAt": "2026-11-03T12:00:00.000Z"
  },
  "followedArtists": ["Artist_101", "Artist_204"],
  "acquiredTickets": [
    {
      "eventId": "EVT_5501",
      "artistName": "Real Artist",
      "section": "Pit 1",
      "pricePaid": 0
    }
  ],
  "purchasedMerch": [
    {
      "itemId": "ITEM_801",
      "title": "Tour Hoodie",
      "size": "L"
    }
  ],
  "activeEvents": {
    "EVT_5501": {
      "countdownMs": 0,
      "status": "WAITING_FOR_USER"
    }
  }
}
