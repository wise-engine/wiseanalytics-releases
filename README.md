# WiseAnalytics Documentation

![WiseAnalytics Logo](screenshots/logo.png)

**WiseAnalytics** is a powerful desktop stock analytics application which provides a comprehensive suite of widgets for tracking stocks, analyzing performance, backtesting strategies, and managing your portfolio.

---

## Table of Contents

- [Getting Started](#getting-started)
- [Connecting Your Broker](#connecting-your-broker)
  - [Zerodha](#zerodha)
  - [Angel One](#angel-one)
- [Interface Overview](#interface-overview)
- [Widgets Catalog](#widgets-catalog)
  - [Watchlist Widgets](#watchlist-widgets)
  - [Portfolio Widgets](#portfolio-widgets)
  - [Analysis Widgets](#analysis-widgets)
  - [Charts Widgets](#charts-widgets)
  - [Research Widgets](#research-widgets)
  - [Fundamentals Widgets](#fundamentals-widgets)
  - [Miscellaneous Widgets](#miscellaneous-widgets)
- [Settings & Configuration](#settings--configuration)
- [Troubleshooting](#troubleshooting)

---

## Getting Started

### System Requirements

- **Operating System:** Windows 10+, macOS 12+, or Linux (Ubuntu 20.04+)
- **RAM:** 4 GB minimum (8 GB recommended)
- **Disk Space:** 200 MB free space
- **Internet:** Required for live data and broker connectivity

### Installation

1. **Download** the latest release for your operating system from the [Releases page](https://github.com/wise-engine/wiseapp/releases)
2. **Run the installer** and follow the on-screen instructions
3. **Launch WiseAnalytics** from your applications menu or desktop shortcut

### First-Time Setup

1. Open WiseAnalytics
2. Sign in with your account credentials
3. Connect your broker (see [Connecting Your Broker](#connecting-your-broker))
4. Start adding widgets to your workspace

---

## Connecting Your Broker

WiseAnalytics connects to your broker via API to fetch live market data, execute trades, and manage your portfolio. You need an active trading account with one of the supported brokers.

### Supported Brokers

| Broker | API Type | Authentication |
|--------|----------|----------------|
| Zerodha | Kite Connect | API Key + API Secret |
| Angel One | Smart API | Client ID + Password + API Key + TOTP |

### Zerodha

To connect your Zerodha account:

1. **Get your API credentials:**
   - Log in to [Kite Connect](https://kite.zerodha.com/connect/login)
   - Go to **Apps** → **Create a new app**
   - Note down your **API Key** and **API Secret**

2. **Connect in WiseAnalytics:**
   - Open the **Connectors** widget
   - Click **Connect** on the Zerodha card
   - Enter your **API Key** and **API Secret**
   - Click **Connect**
   - Complete the login in the browser window that opens
   - Your session will be validated and connected

3. **Session Management:**
   - Sessions typically last for the trading day
   - Use **Reconnect** to refresh an expired session
   - Credentials are saved securely for quick reconnection

### Angel One

To connect your Angel One account:

1. **Get your API credentials:**
   - Log in to [Angel One Smart API](https://smartapi.angelone.in/)
   - Go to **My Apps** → **Create a new app**
   - Note down your **Client ID**, **API Key**, and **TOTP Secret**
   - Your **Password** is your Angel One login password

2. **Connect in WiseAnalytics:**
   - Open the **Connectors** widget
   - Click **Connect** on the Angel One card
   - Enter your **Client ID**, **Password**, **API Key**, and **TOTP Secret**
   - Click **Connect**
   - The TOTP will be generated automatically for future logins
   - Your session will be validated and connected

3. **Session Management:**
   - Angel One uses TOTP-based authentication
   - Sessions are refreshed automatically
   - Use **Reconnect** if your session expires

### Managing Connections

The Connectors widget provides these actions:

| Action | Description |
|--------|-------------|
| **Connect** | Establish a new connection to the broker |
| **Disconnect** | End the current session (credentials are saved) |
| **Reconnect** | Re-establish connection using saved credentials |
| **Revoke** | Delete all saved credentials and tokens |

### Troubleshooting Broker Connection

| Issue | Solution |
|-------|----------|
| "Broker not connected" | Open Connectors widget and click Connect |
| "Session expired" | Click Reconnect to refresh your session |
| "Invalid credentials" | Click Revoke and re-enter your API credentials |
| "TOTP failed" (Angel One) | Re-enter your TOTP Secret in the Connect dialog |
| Rate limit exceeded | Wait a few minutes and try again |

---

## Interface Overview

![WiseAnalytics Home](screenshots/home.png)

The WiseAnalytics interface consists of four main areas:

### 1. Top Bar
- **Workspace tabs** for organizing different layouts
- **Settings** button to customize display and data preferences
- **Changelog** and **Help** access

### 2. Sidebar (Left)
- **Workspace list** with add/rename/delete options
- **Widget palette** to drag widgets onto the workspace

### 3. Main Area (Center)
- **Widget grid** where all widgets are displayed
- **Drag and drop** to reposition and resize widgets

### 4. Right Panel
- **Watchlist** and **Holdings** tabs for quick access
- **Resizable** by dragging the left edge

---

## Widgets Catalog

WiseAnalytics includes 18 enabled widgets organized into 7 categories.

---

## Watchlist Widgets

### Watchlist

![Watchlist Widget](screenshots/watchlist.png)

**Purpose:** Track your favourite stocks and indices at a glance.

**Features:**
- Multiple watchlist tabs (create, rename, delete)
- Live price updates with % change, volume, and gap data
- Column customization (Industry, Exchange, Gap, From Day High/Low, Volume)
- Sort by any column (click column headers)
- Per-symbol notes (click the note icon or use context menu)
- Move/copy symbols between watchlists
- CSV import/export support
- Symbol-linked to other widgets

**How to Use:**
1. Click the search bar and type a stock symbol
2. Select from suggestions to add to the current watchlist
3. Use the settings gear icon to customize visible columns
4. Click a symbol to send it to linked widgets

---

### Market Overview

![Market Overview Widget](screenshots/market-overview.png)

**Purpose:** View market indices and sector constituents with price and gap data.

**Features:**
- NSE and BSE market indices
- Sector-wise stock lists
- Live price and percentage changes
- Click any stock to open it in linked widgets

**How to Use:**
1. Select an index or sector from the dropdown
2. View constituent stocks with their live prices
3. Click any row to link the symbol to other widgets

---

## Portfolio Widgets

### Holdings

![Holdings Widget](screenshots/holdings.png)

**Purpose:** View all the stocks you currently own.

**Features:**
- Current value and P&L for each holding
- Quantity and average buy price
- Day change and total returns
- Symbol-linked for analysis

---

### Positions

![Positions Widget](screenshots/positions.png)

**Purpose:** View open positions with entry price and P&L.

**Features:**
- Real-time P&L calculation
- Entry price and quantity
- Position status (open/closed)
- Quick exit options

---

## Analysis Widgets

### Performance

![Performance Widget](screenshots/performance.png)

**Purpose:** Analyze yearly and monthly returns for any stock.

**Features:**
- Monthly heatmap with color-coded returns (green for gains, red for losses)
- Daily heatmap (weekdays vs months)
- Gap vs Day heatmap for gap analysis
- Expandable year-by-year breakdown
- Yearly summary with best/worst months
- Broker session support (Zerodha, Angel One)
- Configurable date range

**How to Use:**
1. Enter a stock symbol in the search bar
2. Select your broker and date range
3. Click **Fetch** to load performance data
4. Switch between **Heatmap** and **Table** views
5. Use tabs to switch between **Monthly**, **Daily**, and **Gap vs Day**

**Symbol-Linked:** Yes

---

### Comparison Analysis

![Comparison Widget](screenshots/comparison.png)

**Purpose:** Compare cumulative returns of multiple stocks over time.

**Features:**
- Add multiple symbols for comparison
- Interactive line chart
- Normalized returns (base 100)
- Configurable time period

**How to Use:**
1. Add symbols using the search bar
2. Click **Fetch** to generate comparison chart
3. Hover over the chart to see exact values

**Symbol-Linked:** Yes

---

### Event Analysis

![Event Analysis Widget](screenshots/event-analysis.png)

**Purpose:** Analyze how a stock behaves before and after events defined in a CSV file.

**Features:**
- Upload CSV with event dates
- Analysis windows from 1 day to 6 months before/after
- Statistical summary of returns
- Visualization of average price behavior around events

**How to Use:**
1. Prepare a CSV with event dates
2. Upload the CSV using the import button
3. Select the stock symbol
4. View the analysis results

**Symbol-Linked:** Yes

---

## Charts Widgets

### Historical Data

![Historical Data Widget](screenshots/historical.png)

**Purpose:** View price history, OHLC, and volume for any symbol.

**Features:**
- Configurable timeframe (1m, 5m, 15m, 1h, 1d)
- Date range selection
- OHLCV data table
- Export to CSV

**How to Use:**
1. Enter a stock symbol
2. Select timeframe and date range
3. Click **Fetch** to load data

**Symbol-Linked:** Yes

---

### Charts

![Charts Widget](screenshots/charts.png)

**Purpose:** Interactive candlestick charts with pan, zoom, and technical indicators.

**Features:**
- Candlestick chart with OHLCV data
- Pan and zoom (mouse wheel and drag)
- Technical indicators (SMA, EMA, RSI, ATR)
- Drawing tools (trendlines, horizontal lines, ranges)
- Volume overlay
- Quarter and day highlight bands
- Save/load chart layouts
- Y-axis scale control

**How to Use:**
1. Enter a symbol and select timeframe
2. Click **Fetch** to load the chart
3. Use toolbar to add indicators or drawings
4. Drag the chart to pan, scroll to zoom
5. Double-click to reset view

**Drawing Tools:**
- **Trendline:** Draw lines between two points
- **Horizontal Line:** Add a horizontal reference line
- **Range:** Highlight a price range
- **Measure:** Measure distance between points

**Symbol-Linked:** Yes

---

## Research Widgets

### Screener

![Screener Widget](screenshots/screener.png)

**Purpose:** Screen index, sector, and industry groups with technical indicator filters.

**Features:**
- 22+ technical indicators (RSI, ATR, EMAs, Volume, Returns, 52W High/Low, etc.)
- Multiple filter conditions (AND/OR logic)
- Cross-series comparisons (e.g., RSI crosses above SMA)
- Index and sector universe selection
- Group Only mode (scan group names)
- Sort and hide columns
- Download results as CSV
- Add matches to watchlist

**Available Indicators:**
| Indicator | Description |
|-----------|-------------|
| Close Price | Current closing price |
| % Change | Daily percentage change |
| Volume | Trading volume |
| Gap % | Opening gap percentage |
| RSI (14) | Relative Strength Index |
| ATR (14) | Average True Range |
| EMA 20/50/100/200 | Exponential Moving Averages |
| Avg Volume (10) | 10-day average volume |
| Dist. from 52W High/Low % | Distance from 52-week extremes |
| Return 5D/10D/30D/6M/12M | Period returns |

**How to Use:**
1. Select a universe (index or sector) from the dropdown
2. Add filter conditions using the conditions panel
3. Click **Run Scan** to find matching stocks
4. Sort results by clicking column headers
5. Export to CSV or add to watchlist

---

### Backtest

![Backtest Widget](screenshots/backtest.png)

**Purpose:** Backtest entry/exit strategies on historical data with risk management.

**Features:**
- Configurable entry/exit conditions
- Long and short strategies
- Positional and intraday modes
- Risk management (stop loss, target, trailing stop)
- Position sizing (fixed or risk-based)
- Multiple timeframes (1m to 1d)
- Equity curve and drawdown visualization
- Detailed trade log with grouping
- Strategy history with save/load

**Strategy Configuration:**
- **Entry Conditions:** RSI, EMA, SMA, ATR, Volume, Price crossovers
- **Exit Conditions:** Same indicators as entry
- **Risk Management:** Fixed %, ATR-based, or % of capital
- **Position Sizing:** Fixed size or risk percentage

**Analytics Metrics:**
- Net Profit/Loss
- Win Rate
- Total Trades (Long/Short)
- Max Drawdown
- Sharpe Ratio
- Average Win/Loss Ratio
- Max Consecutive Losses
- Average Holding Period

**How to Use:**
1. Select symbols (manual or CSV import)
2. Configure strategy parameters in the Strategy tab
3. Set entry/exit conditions with AND/OR logic
4. Configure risk parameters (stop loss, target, trailing)
5. Click **Run Backtest** to execute
6. View results in the Results tab
7. Access previous backtests in the History tab

---

### Option Chain

![Option Chain Widget](screenshots/option-chain.png)

**Purpose:** View option premiums and Greeks for a selected strike.

**Features:**
- Calls and puts display
- Strike price selection
- Premium and Greeks data
- Implied volatility
- Open interest

**Symbol-Linked:** Yes

---

### News

![News Widget](screenshots/news.png)

**Purpose:** View latest market headlines with source and publish time.

**Features:**
- Real-time news feed
- Source attribution
- Publish timestamps
- Article links

---

## Fundamentals Widgets

### Fundamentals

![Fundamentals Widget](screenshots/fundamentals.png)

**Purpose:** View balance sheet, P&L, and ratios from Screener.

**Features:**
- Company overview and metadata
- Multiple data sections (tabs):
  - Balance Sheet
  - Profit & Loss
  - Cash Flow
  - Ratios
  - Shareholding
- Quarterly and yearly comparisons
- Source links to original data

**How to Use:**
1. Enter a stock symbol
2. Click **Fetch** to load fundamentals
3. Switch between tabs to view different sections
4. Click "View on Screener" for detailed analysis

**Symbol-Linked:** Yes

---

## Miscellaneous Widgets

### Custom Widget

**Purpose:** A collection of frequently used widgets in one place.

**Features:**
- Combine multiple widgets in a single view
- Customizable layout
- Quick access to your most-used tools

---

### Notes

![Notes Widget](screenshots/notes.png)

**Purpose:** Write markdown notes organized into sections.

**Features:**
- Markdown editor
- Section-based organization
- Auto-save to .md files
- Preview mode

---

### Connectors

![Connectors Widget](screenshots/connectors.png)

**Purpose:** Connect third-party apps like brokers and news feeds.

**Features:**
- Broker integration (Zerodha, Angel One)
- OAuth authentication
- Session management
- Live data streaming

---

## Settings & Configuration

### Display Settings

| Setting | Description |
|---------|-------------|
| Main Section | Dark/Light theme for the main workspace |
| Top Bar | Dark/Light theme for the top bar |
| Side Bar | Dark/Light theme for the sidebar |
| Right Panel | Dark/Light theme for the right panel |
| Workspace Backgrounds | Custom background images per workspace |
| Default Workspace | Workspace that opens on sign-in |

### Data Settings

| Setting | Description |
|---------|-------------|
| Historical Data Broker | Select broker for historical data (Zerodha/Angel One) |

---

## Troubleshooting

### Common Issues

| Issue | Solution |
|-------|----------|
| "Broker not connected" | Open Connectors widget and click Connect |
| "No data available" | Check broker session status; click Reconnect if needed |
| Chart not loading | Ensure broker session is active, then click Fetch |
| Screener returns no results | Verify universe selection and filter conditions |
| Widget not updating | Refresh the widget or restart the app |
| App not launching | Check if another instance is running; restart your computer |
| Slow performance | Close other applications; ensure stable internet connection |
| Login failed | Verify your email and password; check internet connection |

### Broker Session Expiry

If your broker session expires during use:
1. Open the **Connectors** widget
2. Click **Reconnect** for your broker
3. For Angel One: TOTP is generated automatically
4. For Zerodha: Complete the login in the browser window
5. Your session will be restored automatically

### Getting Help

If you continue to experience issues:
- Check the [FAQ](https://github.com/wise-engine/wiseapp/wiki/FAQ)
- Report bugs on [GitHub Issues](https://github.com/wise-engine/wiseapp/issues)
- Contact support at wiseanalytics.in@gmail.com

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Enter` | Fetch data in active widget |
| `Escape` | Close dialogs/dropdowns |
| `Delete` / `Backspace` | Delete selected drawing (Charts) |
| `Ctrl + Scroll` | Pan chart vertically |

---

## Support

For issues and feature requests, visit: [GitHub Issues](https://github.com/wise-engine/wiseapp/issues)

---

*Last updated: September 2026*
