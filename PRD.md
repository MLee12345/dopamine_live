# Product Requirements Document

**Project Name:** DopamineLive  
**Version:** 1.0  
**Status:** Approved  
**Target Platform:** Responsive, desktop-first single-page web app  

---

## Who It's For

DopamineLive is for live music fans who enjoy the rush of finding a good show, choosing seats, claiming a ticket, entering a virtual stage, and grabbing artist merch without spending real money or risking a real checkout.

The primary user is a fan who wants a fast, low-stakes version of high-demand ticketing: search artists and venues, filter by city/date/price, preview seats and tracks, use a virtual wallet, and keep a personal history of virtual tickets, concerts attended, and merch collected.

The experience supports both guest users and lightweight demo accounts. Guest and member sessions stay separate, and their saved passes, wallet balance, merch carts, profile history, and daily deal state persist locally in the browser.

---

## Design Claim

DopamineLive turns the stressful parts of ticketing and merch drops into a satisfying simulation: the interface should feel like a real live-event marketplace, but every high-pressure moment is softened into a clear, reversible, local-only interaction.

The product should balance two moods:

- A clean marketplace for discovery, filters, seat maps, ticket review, and wallet visibility.
- A darker, high-energy concert layer for stage entry, playlist playback, visualizer controls, merch queue progress, and hold-to-confirm checkout moments.

The user should always understand that this is a demo. The site can use convincing patterns such as seat holds, checkout timers, verified-fan labels, limited stock, daily deals, and crowd activity, but it must clearly remain a virtual ticket, wallet, merch, and concert simulator.

---

## Three Must-Haves

### 1. Discover and Claim Virtual Tickets

Users must be able to browse a large simulated live-event catalog, search by artist/venue/city, filter by location/date/price, sort results, and open a show detail flow.

The ticket flow must include:

- Artist, venue, city, date, price, and event imagery.
- A seat map with selectable venue sections and per-section pricing.
- Ticket quantity controls and a clear calculated total.
- A checkout review with a visible 20-second seat hold.
- A "press and hold to buy" action that adds the ticket to the user's virtual ticket wallet.

### 2. Keep a Persistent Local Simulation

Users must be able to use DopamineLive without a backend or real payment flow. All prototype state should be saved on the device with browser storage.

The local simulation must persist:

- Current guest or demo-account session.
- Virtual wallet balance, custom top-ups, timed wallet rewards, and daily wheel deal state.
- Saved tickets and ticket badge counts.
- Saved merch carts, merch purchases, and concert attendance history.
- Editable member profile name and city.

Resetting an account must clear only the current guest or member session's saved demo data while keeping the prototype usable.

### 3. Enter the Stage and Buy Virtual Merch

After claiming a ticket, users must be able to manage passes from the ticket wallet and enter a virtual stage when the show is ready.

The stage and merch loop must include:

- A live-stage view with artist and venue context.
- Playlist controls, play/pause behavior, viewer-count ambience, fullscreen stage mode, and visualizer color controls.
- A merch queue interaction that moves the user to the front through a low-friction tap/progress mechanic.
- A merch shop with item imagery, size/color options where applicable, quantity controls, scarcity messaging, cart totals, and a 20-second booth checkout.
- A "press and hold to confirm" merch purchase that deducts from the virtual wallet and records the merch in profile history.

---

## What We're Not Doing

DopamineLive is not issuing real tickets, reserving venue inventory, processing real payments, or contacting payment processors. Any card labels, fees, taxes, verified checkout language, stock warnings, queue movement, and ticket holds are interface simulations.

DopamineLive is not building a backend account system. Demo usernames, passwords, wallet balances, passes, profile history, and carts stay in local browser storage only.

DopamineLive is not integrating with live ticketing, artist, venue, inventory, or commerce APIs. The event catalog, seat maps, merch items, deals, stage behavior, and profile history are generated or stored locally in the app.

DopamineLive is not optimizing for production security, fraud prevention, fulfillment, accessibility certification, or commercial scale. This PRD covers the self-contained prototype experience currently represented by the website.
