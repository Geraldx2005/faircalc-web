# 📦 Label & Ribbon Cost Calculator

A modern, responsive, Electron-powered calculator for estimating **label printing cost**, **ribbon roll cost**, **TTR usage**, and **combined pricing**.  
Built with **React + Tailwind + Electron** for a smooth desktop experience.

---

## ✨ Features

### 🟦 Label Calculator
- Enter **label width & height** in *mm* or *inch*
- Auto-converts units internally
- Calculates:
  - **Cost per 1000 labels**
  - Cost is based on sq. inch pricing
- Clean UI with dynamic currency formatting

### 🟪 Ribbon Calculator
- Enter ribbon **width**, **length**, **rate**, **how many up**, and **ordered quantity**
- Calculates:
  - **Cost per ribbon roll**
  - **Number of labels per ribbon**
  - **Printing cost per 1000 labels**
  - **Required number of TTR rolls**
  - **Total cost including TTR**
- Fully synced with label computations

### 🧩 Additional Features
- Smooth Expandable TTR section  
- Custom designed inputs & segmented switch  
- Fully scrollable UI with **custom scrollbar**  
- Designed to work as a **desktop app** (Electron)

---

## 📸 Tech Stack

| Layer | Tech |
|-------|------|
| UI | React + Tailwind CSS |
| Desktop App | Electron |
| Styling | Custom components + Tailwind utilities |
| State Logic | React State Hooks |
| Build Tool | Vite (if used) |

---

## 📁 Folder Structure

```
project/
│
├── electron/
│   ├── main.js / main.cjs     # Electron main process
│   ├── preload.cjs            # Exposed APIs
│   └── assets/                # App icon, etc.
│
├── renderer/
│   ├── src/
│   │   ├── App.jsx            # Main UI
│   │   ├── components/
│   │   │   ├── SimpleInput.jsx
│   │   │   ├── SimpleButton.jsx
│   │   │   ├── SegmentedButton.jsx
│   │   │   ├── ExpandableSection.jsx
│   │   │   └── RadioOption.jsx
│   │   └── index.css          # Tailwind + custom scrollbar
│   └── dist/                   # Compiled React build
│
└── package.json
```

---

## 🚀 Running the App

### 1️⃣ Install Dependencies

```sh
npm install
```

### 2️⃣ Run React Dev Server

```sh
npm run dev
```

### 3️⃣ Start Electron

```sh
npm run electron
```

---

## 📦 Building the Desktop App

```sh
npm run build
npm run electron-build
```

This generates a standalone executable (EXE) depending on your OS.

---

## ⚙️ Key Logic Highlights

### Label Cost Formula

```
area(in sq inch) = (width_mm / 25.4) * (height_mm / 25.4)
cost_per_label = area * rate
cost_per_1000 = cost_per_label * 1000
```

### Ribbon Roll Formula

```
areaSqM = (ribbonWidth_mm / 1000) * ribbonLength_m
cost_per_roll = areaSqM * rateSqMtr

labels_per_ribbon = floor( ribbonLength_m / labelHeight_m ) * howManyUp

printing_cost_per_1000 = (cost_per_roll / labels_per_ribbon) * 1000
```

---

## 🎨 Custom Scrollbar Example

```css
.minimal-scrollbar::-webkit-scrollbar {
  width: 6px;
}
.minimal-scrollbar::-webkit-scrollbar-thumb {
  background: #2b2b2b;
  border-radius: 6px;
}
```

---

## 🛠 Future Improvements
- Export results as PDF  
- Dark mode  
- Save presets  
- Cloud sync for label/ribbon templates  

---

## 👨‍💻 Author
Built with ❤️ and caffeine.

---

## 📜 License
MIT License (or any license you choose)

---
