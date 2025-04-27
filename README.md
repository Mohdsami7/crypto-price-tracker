# Crypto Price Tracker

A responsive React + Redux Toolkit application that simulates real-time cryptocurrency price tracking with a CoinMarketCap-like interface.

# video link 
https://drive.google.com/file/d/19-K3SH1V5PPcBICRT6GgbJl4hdByZBZp/view?usp=sharing
## Setup Instructions 

1. **Run the Application**:
   - Open the `index.html` file in a modern web browser.
   - No additional setup is required as all dependencies are loaded via CDN.

2. **Dependencies**:
   - React 18.2.0
   - ReactDOM 18.2.0
   - Redux Toolkit 1.9.5
   - React-Redux 8.1.1
   - Tailwind CSS (via CDN)
   - Babel (for JSX transformation)

3. **Development**:
   - The app is self-contained in a single `index.html` file.
   - To modify, edit the `<script type="text/babel">` section.
   - Ensure an internet connection for CDN-hosted dependencies.

## Tech Stack & Architecture

### Tech Stack
- **React**: For building the UI components.
- **Redux Toolkit**: For state management using `createSlice` and `configureStore`.
- **Tailwind CSS**: For responsive styling.
- **Babel**: For JSX transformation in the browser.
- **CDN**: Hosts all dependencies for simplicity.

### Architecture
- **State Management**:
  - Redux Toolkit manages all crypto asset data in a single `crypto` slice.
  - `createSlice` defines the state and `updateAsset` reducer.
  - Selectors (`useSelector`) optimize re-renders by accessing only necessary state.
- **Components**:
  - `App`: Initializes the mock WebSocket and wraps the app with `Provider`.
  - `CryptoTable`: Renders the responsive table and maps assets to `CryptoRow`.
  - `CryptoRow`: Displays individual asset data with formatted numbers and color-coded percentage changes.
- **Real-Time Updates**:
  - A `MockWebSocket` class simulates WebSocket behavior using `setInterval`.
  - Randomly updates price, percentage changes, and 24h volume every 1–2 seconds.
  - Dispatches `updateAsset` actions to Redux to update the store.
- **Responsive Design**:
  - Tailwind CSS ensures the table is responsive with horizontal scrolling on smaller screens.
  - Flexbox and grid utilities align content properly.
- **Data**:
  - Initial data for 5 assets (BTC, ETH, USDT, BNB, ADA) is hardcoded.
  - 7-day charts use placeholder images for simplicity.

### Features
- Displays a table with columns: #, Logo, Name, Symbol, Price, 1h %, 24h %, 7d %, Market Cap, 24h Volume, Circulating Supply, Max Supply, 7D Chart.
- Color-coded percentage changes (green for positive, red for negative).
- Simulated real-time updates via mock WebSocket.
- Fully managed state with Redux Toolkit, no local component state.
- Responsive table design for mobile and desktop.

### Notes
- The 7D chart is a static placeholder image. In a production app, this could be replaced with a charting library like Chart.js.
- The mock WebSocket generates random updates for demonstration. A real WebSocket would connect to a crypto exchange API (e.g., Binance, Coinbase).
- All formatting (prices, percentages, numbers) uses locale-aware methods for readability.