# 📧 Email Template Component Library

This repository contains the foundational HTML structure and a modular library of reusable blocks for creating fully responsive, cross-client compatible email campaigns. The blocks are designed to be easily integrated into any Email Service Provider (ESP) using standard templating logic (e.g., Jinja, Liquid).

## 🚀 Overview

This framework is built using nested tables and relies heavily on inline CSS and conditional MSO (Microsoft Outlook) code to ensure consistent rendering across desktop, webmail, and mobile clients.

All templates are centered and constrained to a maximum width of **640px**. Blocks are mobile-responsive, with most elements utilizing the `.stack` class to ensure content columns drop to full width on mobile devices (except the "Two Buttons" block, which remains side-by-side).

## 🗂️ Template Structure

The Master Template sets the foundation for every email.

### **Master Template (`master.html`)**

| Section | Purpose | Notes |
| :--- | :--- | :--- |
| **Preamble/DOCTYPE** | Sets the email standard and encoding. | Includes Outlook VML setup and conditional mobile styles. |
| **`<body>`** | The main container. | Sets default background and text styles. |
| **Preheader** | Hidden text visible in the inbox preview pane. | **Critical for engagement metrics.** |
| **`content_table`** | The main container (`width="640px"`) for all modular blocks. | Every block must be inserted within this table. |
| **Block Inclusion** | Placeholder for injecting modular blocks. | Example: `{% include 'blocks/header.html' %}` |

***

## 🧩 Modular Content Blocks (9 Total)

The core strength of this library is its collection of reusable blocks, each corresponding to a distinct file in the `blocks/` directory.

### **1. Header (`header.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| Contains the main logo and navigation links. The logo is centrally aligned. Links are typically non-stacking to maintain the navigation bar appearance on mobile. | `LOGO_URL`, `NAV1_TEXT`, `NAV1_URL`, `NAV2_TEXT`, `NAV2_URL`, etc. | Logo image source, text copy, and destination URLs for all navigation links. |

### **2. Solo Image (`solo-image.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| A full-width content image (640px wide). Ideal for hero sections or banner breaks. The image must be uploaded to a reliable CDN. | `IMAGE_URL`, `IMAGE_ALT_TEXT`, `IMAGE_LINK_URL` | Image source, descriptive alt text, and the hyperlink destination. |

### **3. Headline (`headline.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| A simple block for displaying main content headers or subheadings. It is full-width with padding. | `HEADLINE_TEXT` | Text copy, font size, and color (via inline CSS on the surrounding `<td>`). |

### **4. Three Images (Non-Stacking) (`three-images-non-stacking.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| Displays three distinct images side-by-side, each occupying roughly one-third of the width. **Crucially, this block is designed NOT to stack on mobile,** keeping all three elements horizontal. | `IMAGE1_URL`, `IMAGE1_LINK`, `IMAGE2_URL`, `IMAGE2_LINK`, `IMAGE3_URL`, `IMAGE3_LINK` | Image sources and their corresponding hyperlinks for all three images. |

### **5. Spacer (`spacer.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| Provides vertical white space for design separation. Height is controlled via inline styles. | (None required) | The `height` property (e.g., `height:24px;`) can be customized to adjust vertical spacing. |

### **6. Divider (`divider.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| Creates a simple horizontal line to visually separate content sections. Ideal for use after a main copy block or before a new product area. | (None required) | Line color, thickness (height), and width can be adjusted via inline CSS styles. |

### **7. Two Buttons (Non-Stacking) (`two-buttons.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| Places two full-width CTA buttons side-by-side, with strategic padding for separation. **The columns are intentionally designed NOT to stack on mobile** to force a dual choice display. | `TEXT1_PLACEHOLDER`, `URL1_PLACEHOLDER`, `TEXT2_PLACEHOLDER`, `URL2_PLACEHOLDER` | Text copy and destination URLs for both buttons. |
| **⚠️ Customization Note:** Background and text colors must be updated in the **HTML** (span), **VML `fillcolor`**, and **VML `stroke color`** for both buttons to ensure Outlook compatibility. |

### **8. Footer (`footer.html`)**

| Description | Placeholders | Customization |
| :--- | :--- | :--- |
| The mandatory closing component containing four promotional benefits, social links, legal links (`Privacy Policy`, `Unsubscribe`), and company address information. | **Benefits (x4):** `BENEFIT*_ICON_URL`, `BENEFIT*_URL`, `BENEFIT*_TEXT`. **Social (x4):** `SOCIAL_*_URL`. **Legal:** `PRIVACY_POLICY_URL`, `ADDRESS_TEXT`. | All image sources, links, and text copy. ESP variables for `UNSUBSCRIBE` (`{{ consent.page }}`) and `VIEW ONLINE` (`{{ email.view }}`) should **NOT** be changed. |
