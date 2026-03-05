# GreenRealtors Property Listing System

A lightweight, multi-page property listing web app for real estate teams. The public can browse available properties, while only authorized staff can add or remove listings.

No frameworks, no build tools — just three HTML files that work right out of the box.

---

## Pages

| File | Purpose |
|---|---|
| `index.html` | Public-facing listings page |
| `login.html` | Staff login |
| `admin.html` | Protected dashboard for managing properties |

---

## Getting Started

Download or clone the project, then open `index.html` in your browser. That's it.

All three files need to be in the same folder.

---

## Staff Access

To manage listings, click **Staff Login** in the top-right corner of the public page.

Default credentials:

| Username | Password |
|---|---|
| admin | green2025 |
| staff | realty123 |

> **Note:** These credentials are hardcoded for demo purposes. Before deploying to a real environment, replace them with a proper authentication backend.

To change or add credentials, open `login.html` and find this section near the bottom:

```js
const STAFF_CREDENTIALS = [
  { username: 'admin', password: 'green2025' },
  { username: 'staff', password: 'realty123' }
];
```

---

## How It Works

- Properties are stored in the browser's `localStorage`, so they persist between sessions on the same device.
- Staff authentication uses `sessionStorage` — the session clears when the browser tab is closed.
- Anyone who tries to access `admin.html` directly without logging in is automatically redirected to the login page.

---

## Customization

**Colors** — All colors are defined as CSS variables at the top of each file's `<style>` block:

```css
--forest: #1a3a2a;
--sage:   #4a7c59;
--mint:   #a8d5b5;
--cream:  #f8f4ee;
```

Change these to match your brand.

**Company name** — Search for `GreenRealtors` across the three files and replace it with your own.

---

## Limitations

Since this is a frontend-only project, keep these in mind:

- Data is stored per browser/device — properties added on one device won't appear on another.
- Credentials are visible in the source code — not suitable for production without a backend.
- There is no image upload support for properties yet.

For a production setup, you'd want a backend (e.g. Node.js, Firebase) handling auth and a shared database for listings.

---

## File Structure

```
/
├── index.html     # Public listings
├── login.html     # Staff login
├── admin.html     # Admin dashboard
└── README.md
```