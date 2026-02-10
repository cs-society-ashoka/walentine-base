

# Interactive Valentine — Full Build Plan

## Overview
A static React app with 6 unique, multi-stage interactive Valentine templates. Users fork the repo, edit `src/config.ts` with their own names/messages/photos, and deploy to GitHub Pages. No backend needed.

---

## 1. Foundation & Config

- **HashRouter** for GitHub Pages compatibility
- **Central `src/config.ts`** file with: `senderName`, `recipientName`, `message`, `photos` (array of URLs), and `questions` (array of stage text strings)
- Install **framer-motion** for animations and **canvas-confetti** for the finale
- Placeholder photos from `picsum.photos`

---

## 2. Landing Page — Template Gallery

- A beautiful gallery page at the root route (`/`)
- Shows 6 cards, each previewing a template with its name, a brief description, and a visual teaser
- Each card links to its template route (e.g., `/#/memory-cloud`)
- Cards grouped into "📸 Photo Templates" and "📝 Text Templates"

---

## 3. Template 1 — "The Memory Cloud" (Dreamy / Ethereal)

**Design:** Soft pastels, floating particles, dreamy blur effects

- **Stage 1 – The Fog:** Screen covered in animated fog/blur. Prompt: "Clear the mist to find us…" User drags cursor/taps to reveal content underneath via a CSS mask effect
- **Stage 2 – The Discovery:** Floating photo bubbles drift around. User must pop 5 bubbles by clicking them (satisfying pop animation)
- **Stage 3 – The Question:** Photos swirl into a heart formation. "Will you be my Valentine?" card fades in with Yes/No. Yes triggers confetti

---

## 4. Template 2 — "The Mixtape" (Retro Music / Warm Tones)

**Design:** Warm oranges, cassette-tape aesthetic, lo-fi vibes

- **Stage 1 – The Cassette:** Illustrated cassette tape labeled "For [Recipient]". Button: "Insert Tape"
- **Stage 2 – The Visualizer:** Music player UI loads. User hits Play. Animated audio visualizer bars play. The sender's message scrolls by like karaoke lyrics
- **Stage 3 – Hidden Track:** "Hidden Track Found!" notification. Clicking reveals: "Track 1: Be My Valentine?" with Yes/No. Yes triggers confetti

---

## 5. Template 3 — "90s Desktop Simulator" (Retro Windows 95)

**Design:** Classic Win95 gray, pixelated fonts, boxy UI

- **Stage 1 – Login:** Windows 95-style login screen. User clicks "Login as [Recipient Name]"
- **Stage 2 – The Glitch:** Desktop loads with photo file icons. Error popups cascade: "CRUSH_DETECTED.exe", "Too_Cute_Error", "Heart_Rate_High". User must close 3-4 popups
- **Stage 3 – Blue Screen of Love:** Closing the last popup triggers a fake BSOD that transitions to pink: "System Failure: I've fallen for you. Will you be my Valentine?" Yes triggers confetti

---

## 6. Template 4 — "The Love Receipt" (Minimal / Trendy)

**Design:** Black & white, monospace font, thermal receipt aesthetic

- **Stage 1 – The Order:** Blank receipt printer. Button: "Print Receipt"
- **Stage 2 – The Calculation:** Receipt "prints" line-by-line with items like "Inside Jokes × ∞", "Late Night Talks", "Butterflies". Typewriter-style animation
- **Stage 3 – The Signature:** Total line: "1 Valentine Needed". Glowing "Sign Here" area. Clicking stamps "APPROVED ✓" as the Yes action. Confetti fires

---

## 7. Template 5 — "The RPG Quest" (Pixel Art / Gamer)

**Design:** Pixel art, 8-bit colors, RPG text boxes

- **Stage 1 – The Map:** Pixel character on a simple map. "It's dangerous to go alone." User clicks to move toward a treasure chest
- **Stage 2 – The Battle:** Turn-based battle UI. A "Loneliness" monster appears. User mashes "Attack with Love ❤️" to drain its HP bar
- **Stage 3 – The Loot:** Monster defeated. Chest opens. RPG text box types out: "You found a Valentine! Equip now?" Yes/No. Yes triggers confetti

---

## 8. Template 6 — "The Sealed Letter" (Elegant / Calligraphy)

**Design:** Cream paper, wax seal red, serif fonts, parchment texture

- **Stage 1 – The Delivery:** Wax-sealed envelope slides onto screen. "For Your Eyes Only"
- **Stage 2 – The Unfolding:** Click to crack the wax seal (crack animation). Click to unfold top flap. Click to unfold bottom flap. Each step has a satisfying paper animation
- **Stage 3 – The Reading:** Letter fully open. Custom message fades in text-by-text. A pen appears. User drags pen to the "Yes ✓" checkbox to complete. Confetti fires

---

## 9. Shared Features Across All Templates

- **Stage tracking** via `useState` (stages 0→1→2→3)
- **Smooth transitions** between stages using framer-motion `AnimatePresence`
- **Confetti explosion** only on final "Yes" click
- **Back to Gallery** button on each template
- **Responsive design** — works on mobile and desktop
- **Config-driven** — all personal content (names, messages, photos) pulled from `config.ts`

