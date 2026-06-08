# 🛒 Retail Analytics — Dynamic Sales Dashboard

---

## 📌 Project Overview

This is a **React.js web application** that dynamically displays sales data for major Indian cities. Users can select a city from a dropdown (or quick-switch pill buttons), and the entire dashboard — stats, bar chart, and line chart — updates instantly **without any page reload**.

The project demonstrates the transition from static HTML pages to a **fully dynamic, data-driven dashboard**.

---

## 🏗️ Component Structure

```
src/
│
├── App.jsx                  ← Root component, renders SalesDashboard
├── SalesDashboard.jsx       ← Main dashboard (city selector + charts + stats)
│   ├── StatCard             ← Reusable stat card (Revenue, Orders, Avg, Growth)
│   └── CustomTooltip        ← Custom recharts tooltip component
│
└── data/
    └── salesData.json       ← Mock JSON: 5 cities × 7-day sales data
```

### Component Responsibilities

| Component | Purpose |
|---|---|
| `SalesDashboard` | Holds city state, reads mock data, renders all child sections |
| `StatCard` | Displays a single KPI with label, value, and accent colour |
| `CustomTooltip` | Formatted tooltip shown on chart hover |

---

## 📊 Features

- ✅ **City Dropdown** — Select from Mumbai, Jaipur, Lucknow, Delhi, Bangalore
- ✅ **Instant Dynamic Update** — No page reload; React state drives all UI changes
- ✅ **KPI Stat Cards** — Total Revenue, Total Orders, Avg Order Value, Growth %
- ✅ **Bar Chart** — Daily revenue per day of the week (Recharts)
- ✅ **Line Chart** — Orders trend across the week (Recharts)
- ✅ **Quick-Switch Pills** — Click city name directly below charts
- ✅ **Animated Transitions** — CSS fadeUp animation on city switch
- ✅ **Responsive Design** — Works on desktop and mobile screens
- ✅ **Mock JSON Data** — Realistic sales figures for 5 Indian cities

---

## 🗂️ Mock Data Structure (`salesData.json`)

```json
{
  "cities": ["Mumbai", "Jaipur", "Lucknow", "Delhi", "Bangalore"],
  "salesData": {
    "Mumbai": {
      "city": "Mumbai",
      "region": "Maharashtra",
      "dailySales": [
        { "day": "Mon", "amount": 124500, "orders": 312 },
        ...7 days
      ],
      "totalRevenue": 1046500,
      "totalOrders": 2615,
      "avgOrderValue": 400,
      "topCategory": "Electronics",
      "growth": "+12.4%"
    },
    ...4 more cities
  }
}
```

---

## 🚀 How to Run the Project

### Prerequisites
- Node.js v18+ installed
- npm or yarn

### Step 1 — Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/retail-sales-dashboard.git
cd retail-sales-dashboard
```

### Step 2 — Install Dependencies
```bash
npm install
```

### Step 3 — Start Development Server
```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **React.js** | UI component framework |
| **Vite** | Build tool / dev server |
| **Recharts** | Bar chart + Line chart |
| **Mock JSON** | Simulated backend data |
| **CSS-in-JS** | Inline styles + keyframe animations |

---

## 📦 Setup from Scratch (if not cloning)

```bash
npm create vite@latest retail-dashboard -- --template react
cd retail-dashboard
npm install
npm install recharts
```

Then replace `src/App.jsx` with the provided `SalesDashboard.jsx` and add `salesData.json` inside `src/data/`.

---

## 🎯 Approach & Design Decisions

1. **Mock data in JSON** — Mimics a real REST API response. In production, this would be replaced by `fetch('/api/sales?city=Mumbai')`.

2. **useState for city selection** — Single source of truth. When `selectedCity` changes, React re-renders only the affected components.

3. **Modular components** — `StatCard` and `CustomTooltip` are extracted so they can be independently tested and reused.

4. **No page reload** — All filtering happens in-memory using JavaScript object lookup (`salesData[selectedCity]`), demonstrating dynamic rendering vs static pages.

5. **Recharts** — Chosen for its React-first API and zero-config responsiveness via `ResponsiveContainer`.

---

## 👨‍💻 Author

**Priya Kumari**  
Full Stack Developer Assignment — W1_A1  
Retail Analytics Platform
