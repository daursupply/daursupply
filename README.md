# Task: Critical Performance Optimization, UI Fixes & Feature Updates for DAUR Supply

**Context & Brand Constraints:**
* **Brand:** DAUR Supply (`daursupply.com`), a Pakistani men's leather footwear brand.
* **Color Palette:** Forest (`#172C27`), Bone (`#F1EBDD`), Sand (`#F4EFE4`), Slate (`#3F4F4A`), Gold (`#A58A64`), Dark Gold (`#7A6443`).
* **Copywriting Rule:** Never use hyphens or em-dashes in any customer-facing UI text, labels, or descriptions (e.g., write ranges as "2 to 4", never "2-4").

Please execute the following tasks in strict order of priority. Do not summarize or skip any item.

---

### 1. CRITICAL PRIORITY: Mobile & Desktop Speed Optimization
Users are bouncing before the site finishes loading, especially on mobile. Treat this as a P0 emergency:
* **Purge Unused Code & Assets:** Audit the entire codebase/theme. Remove all dead JavaScript, unused CSS, unused Liquid/HTML sections, and unreferenced assets. Never load scripts, fonts, or media on pages where they are not actively rendered.
* **Single-Image Fetching on Listings:** On all product collection/listing grids, fetch and render **only one image** per product (the primary selected image). Do not fetch hover/secondary images or extra gallery assets on listing pages.
* **Next-Gen Image Delivery:** Ensure all product and page images are served in the fastest web-ready format (WebP/AVIF with proper responsive `srcset` sizing and lazy loading below the fold, eager/preloaded for the above-the-fold hero).
* **Inline SVG Icons Only:** Replace `story.png` (and any other UI icons) with lightweight inline SVGs (such as a clean SVG feed/story icon) to eliminate extra image network requests.
* **Remove Runway on Mobile:** Completely remove/disable the Runway section on mobile viewports (`display: none` is not enough—prevent its scripts and assets from loading on mobile altogether so it does not clutter or slow down mobile devices).

---

### 2. Product Listings, Home Page & Cart UX
* **Product Card Layout & Space:**
  * Maximize vertical space for the shoe image up to the top of the pair name so the full shoe is clearly visible without obstruction.
  * Move fit notes / subtle badges neatly above or around the top area without covering the shoe itself.
  * Add a subtle, smooth micro-animation when a product card is hovered or active/tapped.
* **Home Page Runner / Showcase Truncation Fix:**
  * In the side detail panel of the home page runner/display, clamp/truncate long product descriptions (e.g., `line-clamp`) so they never overflow or push/hide the shoe's name or price.
* **Sale & Price-Cut Styling (Deep Red):**
  * Style all price-cut cards inside the slider under statuses with a **deep red** background/accent so they immediately read as a sale.
  * Apply this same **deep red** color across the entire site wherever sale elements appear: the "Sale" navigation menu item, percentage-off badges, and sale tags.
* **Cart Drawer / Empty State Behavior:**
  * When a user adds a pair to the cart and clicks outside the cart drawer (or clicks to continue shopping), return them directly to the exact collection/shopping page where they were viewing that pair to minimize extra clicks.

---

### 3. Hero Sections, Vectors & Page-Specific Updates
* **Gifts Page Hero & WhatsApp Card:**
  * Remove the harsh straight vertical/horizontal cut between the image side and text side in the hero. Blend them seamlessly using a soft CSS gradient transition so it looks cohesive and editorial.
  * Redesign the floating `"Eid Mubarak Abu"` message card so it looks like a sleek, DAUR-branded WhatsApp message notification styled as a gift note.
* **Philanthropy Page Hero:**
  * Apply the exact same seamless gradient blend between the text and image sides of the hero section as done on the Gifts page.
* **Hero Vectors & Shoe Sketches Across Other Pages:**
  * Incorporate the uploaded shoe designs and lifestyle/on-foot imagery into the hero sections of the remaining pages so they are clearly visible and well-framed.
  * Convert/render them as clean, lightweight **SVG vectors and minimalist shoe sketches** (using our Forest `#172C27`, Bone `#F1EBDD`, and Gold `#A58A64` palette) so they add elegance without hurting page load speed.

---

### 4. Payment Cards (JazzCash & EasyPaisa) & Bank Accounts Page
* **Footer Link:** Add a clearly visible **"Bank Accounts"** (or Payment Accounts) link in the website footer so customers can access payment details easily.
* **Card Selection & Real Card Dimensions:**
  * Remove the traditional Bank card component; keep **only JazzCash and EasyPaisa** cards.
  * Size and proportion both cards to match **real physical debit/wallet card dimensions** (standard ~1.586:1 aspect ratio).
* **JazzCash Card Details:**
  * Style it in a sleek, authentic JazzCash aesthetic while displaying all account details clearly:
    * **Account Number:** `0319 9628735`
    * **IBAN:** `PK31JCMA1411923199628735`
    * **Till ID & QR Code:** Embed the provided JazzCash Till ID and QR code image.
* **EasyPaisa Card Details:**
  * Match the physical card proportions and style it in a clean EasyPaisa design with the account details and QR code.
* **Interactive QR Enlargement / Card Flip:**
  * Because QR codes on card-sized layouts can be small to scan, add a clear **"Enlarge QR" / "Tap to Scan"** button on the cards. When clicked, smoothly flip/swap the card to show a large, high-contrast, easily scannable QR code on the back of the card (with a button to flip back).

---

### 5. Footer, Table of Contents (TOC) & Functional Verification
* **Verify Email Collection:** Inspect all newsletter / email capture forms across the site. Ensure they actually submit and store customer emails in the backend/Shopify customer list rather than just playing a frontend success animation.
* **Fix Table of Contents (TOC) Z-Index / Overlap:** Fix the sticky TOC on policy/content pages so it stops cleanly above the footer when scrolled to the bottom instead of overlapping footer content.
* **Animated Delivery Van at Very Bottom of Footer:**
  * At the very bottom edge of the footer, add a lightweight CSS/SVG animation of a **DAUR-branded delivery van** loaded with shoe boxes driving slowly across the bottom of the screen. Ensure it runs smoothly on GPU-accelerated transforms (`translateX`) with zero layout shift or performance lag.
