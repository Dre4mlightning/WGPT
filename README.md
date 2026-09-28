# WeatherGPT - AI-Powered Weather & Disaster Intelligence Platform

> **Smart India Hackathon 2026**
> **Theme:** Disaster Management
> **Problem Statement ID:** `SIH26068`
> **Team:** NimbX (Jalpaiguri Emergency Operations Cell)

---

## Overview

**WeatherGPT** is a mobile-first, government-grade weather intelligence and disaster early-warning frontend designed for high-vulnerability regions (centered on the **Sub-Himalayan West Bengal / Teesta River Basin**).

It combines real-time observation telemetry, an **Executive AI Weather Briefing**, **Multi-Sector Weather Impact Assessments**, an interactive **Tactical GIS Weather Radar Console**, multilingual support (English, Hindi, Bengali), and dynamic **Light/Dark theme switching**.

---

## Tech Stack

- **Framework:** React 18 with Vite
- **Styling:** Tailwind CSS (with custom glassmorphism and full dark mode support)
- **Icons:** Lucide React
- **Analytics & Charts:** Recharts
- **GIS & Mapping:** Leaflet & React-Leaflet
- **Routing:** React Router v6
- **Mobile Packaging:** Capacitor 6 (Android native runtime)

---

## Getting Started (Run Locally)

### 1. Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- `npm` or `yarn`

### 2. Install Dependencies
```bash
npm install
```

### 3. Start Development Server
```bash
npm run dev
```
Open **`http://localhost:5173`** in your browser.

---

## Available Scripts

| Command | Action |
|---|---|
| `npm run dev` | Starts Vite local development server with hot-module reloading |
| `npm run build` | Compiles optimized production bundle into `dist/` |
| `npm run preview` | Previews the compiled production build locally |

---

## Key Features

1. **Executive AI Weather Briefing:** Multi-hazard threat index (Orange/Red alerts), peak downpour window, river discharge surge indicators, and simulated audio situation briefing.
2. **8-Point Micro-Telemetry Instrument Matrix:** Real-time atmospheric pressure tendency, dew point, relative humidity, wind velocity azimuth, solar UV index, visibility, and AQI PM2.5/PM10 breakdown.
3. **Multi-Sector Weather Impact Assessments:** Sectoral vulnerability cards for:
   - Agriculture & Tea Estates
   - River Hydrology & Flood Gauges (Teesta & Karala basins)
   - Transportation & Hill Highways (NH-10 & NH-27)
   - Civil Infrastructure & Power Grid
4. **Tactical GIS Radar Map (`/map`):** Interactive Doppler Radar reflectivity (dBZ) swath, river flood inundation buffers, Automatic Weather Stations (AWS), and NDRF relief shelters.
5. **Choosable Light & Dark Themes:** Instant one-click toggle in the header and sidebar.
6. **Multi-Language Support:** Instant switching between English, Hindi (हिन्दी), and Bengali (বাংলা).
7. **Offline Service Abstraction:** Clean mock services (`weatherService.js`, `aiService.js`, `alertService.js`, `locationService.js`) ready to hook into live APIs (IMD / Open-Meteo / Gemini LLM).

---

## Directory Structure

```
weathergpt/
├── index.html
├── package.json
├── tailwind.config.js
├── vite.config.js
├── capacitor.config.json
├── src/
│   ├── main.jsx
│   ├── App.jsx
│   ├── index.css
│   ├── layouts/
│   │   └── AppLayout.jsx
│   ├── pages/
│   │   ├── Home.jsx              # Main telemetry dashboard
│   │   ├── WeatherMapPage.jsx    # GIS Radar & hazard console
│   │   ├── Alerts.jsx            # Disaster alert notifications
│   │   ├── Insights.jsx          # Climate trends & charts
│   │   ├── Chat.jsx              # Conversational AI disaster cell
│   │   └── Profile.jsx           # Preferences & theme selector
│   ├── components/
│   │   ├── common/               # Header, Sidebar, BottomNav, etc.
│   │   ├── weather/              # MainWeatherCard, AIBriefingCard, etc.
│   │   ├── map/                  # Leaflet layers, radar legends, controls
│   │   ├── alerts/               # AlertCard, notification settings
│   │   ├── charts/               # Rainfall and temperature charts
│   │   └── chat/                 # AI chat message bubbles & input
│   ├── context/
│   │   ├── WeatherContext.jsx    # Weather & station state
│   │   ├── ThemeContext.jsx      # Light / Dark theme toggling
│   │   ├── LanguageContext.jsx   # Multilingual i18n
│   │   └── UnitContext.jsx       # Metric / Imperial units (°C/°F)
│   ├── data/
│   │   ├── weatherData.js        # High-density mock telemetry & stations
│   │   ├── alertsData.js         # Disaster hazard alerts data
│   │   ├── insightsData.js       # Historical & forecast chart data
│   │   └── chatData.js           # Pre-configured AI responses
│   └── services/
│       ├── weatherService.js     # Weather data service interface
│       ├── aiService.js          # AI reasoning service interface
│       ├── alertService.js       # Disaster alerts service interface
│       └── locationService.js    # Location resolver
└── android/                      # Capacitor Android native project
```

---

## Building the Android APK (Optional)

1. Build production web assets:
   ```bash
   npm run build
   ```
2. Sync assets with Capacitor:
   ```bash
   npx cap sync android
   ```
3. Compile debug APK using Gradle:
   ```bash
   cd android
   ./gradlew assembleDebug
   ```
The compiled APK will be located at:
`android/app/build/outputs/apk/debug/app-debug.apk`
