# 🟠 Bitcoin URI + QR Code Generator

A modern, clean **Next.js 14 + TypeScript + Tailwind + shadcn/ui** web app that lets users:

- Enter a **Bitcoin wallet address, amount, and optional message** (e.g., invoice #)
- Instantly generate a valid **BIP-21 URI**
- Display the URI as text **and a QR code**
- Copy the URI to clipboard for sharing
- ⚡ Works with all major BTC wallets (Edge, Muun, BlueWallet, etc.)

---

## ✨ Features

- ✅ BIP-21 URI generation (`bitcoin:...`)
- ✅ QR code generation via `qrcode`
- ✅ Input validation
- ✅ Tailwind + shadcn UI components
- 🧠 Clean, scalable layout for future automations
- 📦 Fully typed with TypeScript

---

## 📦 Tech Stack

| Tech         | Description                         |
|--------------|-------------------------------------|
| Next.js 14   | React framework (App Router)        |
| TypeScript   | Static typing                       |
| TailwindCSS  | Utility-first styling               |
| shadcn/ui    | Accessible UI components            |
| qrcode       | QR Code rendering                   |

---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/YOUR_USERNAME/bitcoin-uri-gen.git
cd bitcoin-uri-gen
```

> 🔐 If your repo is private, use GitHub SSH or authenticate with `gh`.

---

### 2. Install Node.js (if not already)

```bash
node -v
```

If missing, install via:

```bash
brew install node
```

Or use [Volta](https://volta.sh) or [nvm](https://github.com/nvm-sh/nvm) to manage versions.

---

### 3. Install Dependencies

```bash
npm install
```

---

### 4. Start the Dev Server

```bash
npm run dev
```

Then open [http://localhost:3000](http://localhost:3000) 🎉

---

## ⚠️ Common Issues

> ❗ **Seeing import errors like `@/components/ui/input` not found?**

You probably haven’t generated the UI components with `shadcn-ui`. Just run:

```bash
npx shadcn-ui@latest add button input card label
```

Then restart your dev server.

---

## 🧱 Project Structure

```
src/
├─ app/
│  └─ page.tsx         # main invoice/QR UI
├─ components/
│  └─ ui/              # shadcn components (input, button, card, etc.)
public/
tailwind.config.ts
tsconfig.json
```

---

## 📌 Next Steps (TODO)

- [ ] 🔄 Pull BTC amounts dynamically from a cart/order system
- [ ] 🧾 Auto-fill `message` field with invoice numbers
- [ ] 🧠 Generate fresh BTC addresses via xpub or backend call
- [ ] 📩 Email the URI and QR to a customer (with invoice PDF)
- [ ] 🧪 Confirm tx using mempool.space or own node
- [ ] 🌐 Deploy to Vercel or Hostinger

---

<details>
<summary>📚 Developer Tips</summary>

- Use `nvm` or `volta` to pin a Node version per project:
  ```bash
  echo "20.11.1" > .nvmrc
  nvm use
  ```

- Restart your TypeScript server in VS Code if imports break:
  `Cmd+Shift+P` → “TypeScript: Restart TS Server”

</details>

---

## ✅ Contributing

Pull requests welcome! If you're using this in your stack or expanding it, feel free to fork and build on it.

---

## 📝 License

MIT — free to use, modify, and commercialize. Attribution welcome but not required.

---

## 🔗 Related

- [BIP-21: URI Format](https://github.com/bitcoin/bips/blob/master/bip-0021.mediawiki)
- [qrcode NPM Package](https://www.npmjs.com/package/qrcode)
- [shadcn/ui Docs](https://ui.shadcn.com/)

---

## 🧱 Build & Deploy (Static Export)

### ➤ If deploying to **Hostinger** or any shared host (non-Node):

You’ll need to build a static version of the site:

1. Edit your `next.config.js` file (create it if missing):

```js
/** @type {import('next').NextConfig} */
const nextConfig = {
  output: 'export',
};

module.exports = nextConfig;
```

2. Build & export your site:

```bash
npm run build
npm run export
```

3. This creates an `out/` folder with static HTML, CSS, and JS — ready for upload.

4. Upload the contents of `out/` to your Hostinger `public_html/` directory or your subdomain folder (like `bitcoin.example.com`).

