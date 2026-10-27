# Fiber Wallet Client-Side Decryptor

A 100% client-side, zero-database, in-memory keystore decryptor designed for Fiber wallet backups (`fiber-wallet-export`).

**Author:** SR485970  
**Follow on X:** [@sumitxbt](https://x.com/sumitxbt)

---

## Security Guarantees
- **Strict Content Security Policy (CSP):** `connect-src 'none'` prevents the browser from sending any outgoing network requests.
- **Zero Storage:** No cookies, `localStorage`, `sessionStorage`, or IndexedDB.
- **In-Memory Cryptography:** Uses browser-native Web Crypto API (`window.crypto.subtle`) for PBKDF2-HMAC-SHA256 and AES decryption.
- **Auto-Destruction:** All memory references are cleared when the window is closed, refreshed, or when clicking "Destroy / Wipe Memory".

## How to Test Locally
1. Double-click `index.html` to open it in Chrome, Brave, Edge, or Firefox.
2. Select or paste your `fiber-wallet-backup-*.json` file.
3. Enter your backup password and click **Decrypt In-Memory**.

## Deploy to Vercel
### Option 1: Vercel CLI
Run in this directory:
```bash
npx vercel
```

### Option 2: GitHub + Vercel Dashboard
1. Push this folder to a GitHub repository.
2. Go to [vercel.com](https://vercel.com) and import the repository.
3. Deploy! Vercel will serve `index.html` statically with all CSP security headers.
