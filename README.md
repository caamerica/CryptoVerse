# Cryptoverse

A modern cryptocurrency and news tracking application built with React, Redux Toolkit, and Ant Design. Get real-time cryptocurrency data, exchange information, and the latest crypto news all in one place.

## Features

- **Cryptocurrency Dashboard**: View live cryptocurrency prices, market cap, and trading volumes
- **Global Stats**: Track overall cryptocurrency market statistics including total market cap and 24h volume
- **Top Cryptocurrencies**: Browse the top cryptocurrencies ranked by market cap
- **Crypto Details**: Get detailed information about individual cryptocurrencies including price history, supply data, and market statistics
- **Crypto News**: Stay updated with the latest cryptocurrency news from Bing News
- **Exchange Information**: Explore cryptocurrency exchanges and their trading volumes
- **Responsive Design**: Fully responsive UI that works on desktop, tablet, and mobile devices

## Tech Stack

- **Frontend Framework**: React 18.2
- **State Management**: Redux Toolkit with RTK Query
- **UI Library**: Ant Design (antd) 5.13
- **Routing**: React Router v6
- **HTTP Client**: Axios
- **Charts**: Chart.js with react-chartjs-2
- **Styling**: Custom CSS with Ant Design components
- **Build Tool**: React Scripts

## Project Structure

```
crypto-app/
├── public/
│   ├── index.html
│   └── _redirects.txt
├── src/
│   ├── app/
│   │   └── store.js                 # Redux store configuration with RTK Query middleware
│   ├── components/
│   │   ├── Cryptocurrencies.jsx     # Cryptocurrencies list component
│   │   ├── CryptoDetails.jsx        # Individual crypto details with price history
│   │   ├── Exchange.jsx             # Exchange information display
│   │   ├── Homepage.jsx             # Main landing page with global stats
│   │   ├── LineChart.jsx            # Price history chart component
│   │   ├── Loader.jsx               # Loading spinner component
│   │   ├── Navbar.jsx               # Navigation bar
│   │   ├── News.jsx                 # Cryptocurrency news feed
│   │   └── index.js                 # Component exports
│   ├── services/
│   │   ├── cryptoApi.js             # Export wrapper for crypto API
│   │   ├── crytpoAPI.js             # RTK Query API for cryptocurrency data
│   │   └── cryptoNewsApi.js         # RTK Query API for cryptocurrency news
│   ├── images/                      # Image assets
│   ├── App.js                       # Main App component with routes
│   ├── App.css                      # Application styles
│   ├── index.js                     # React 18 app entry point
│   └── index.css                    # Global styles
├── .env                             # Environment variables (API keys and URLs)
├── package.json                     # Project dependencies and scripts
└── README.md                        # This file
```

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn package manager
- RapidAPI account with access to:
  - [CoinRanking API](https://rapidapi.com/Coinranking/api/coinranking1)
  - [Bing News Search API](https://rapidapi.com/microsoft-azure-org-microsoft-cognitive-services/api/bing-news-search1)

## Installation

1. **Clone or download the project**:
   ```bash
   cd crypto-app
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   
   Create or update the `.env` file in the project root with your RapidAPI credentials:
   ```env
   REACT_APP_RAPIDAPI_KEY=your_rapidapi_key_here
   REACT_APP_CRYPTO_API_URL=https://coinranking1.p.rapidapi.com/v2
   REACT_APP_CRYPTO_RAPIDAPI_HOST=coinranking1.p.rapidapi.com
   REACT_APP_NEWS_API_URL=https://bing-news-search1.p.rapidapi.com
   REACT_APP_NEWS_RAPIDAPI_HOST=bing-news-search1.p.rapidapi.com
   ESLINT_NO_DEV_ERRORS=true
   ```

## Running the Application

### Development Mode

Start the development server with hot-reload:
```bash
npm start
```

The app will open automatically at `http://localhost:3000`

### Production Build

Create an optimized production build:
```bash
npm run build
```

The build folder will contain the production-ready files.

### Testing

Run the test suite:
```bash
npm test
```

## API Integration

The application uses two main APIs via RapidAPI:

### CoinRanking API v2
- **Base URL**: `https://coinranking1.p.rapidapi.com/v2`
- **Endpoints Used**:
  - `GET /coins?limit={count}` - Get list of cryptocurrencies
  - `GET /coin/{coinId}` - Get detailed info for a specific coin
  - `GET /coin/{coinId}/history?timeperiod={timeperiod}` - Get price history
  - `GET /exchanges` - Get exchange information (requires premium plan)

### Bing News Search API
- **Base URL**: `https://bing-news-search1.p.rapidapi.com`
- **Endpoints Used**:
  - `GET /news?q={query}&safeSearch=Off&textFormat=Raw&freshness=Day&count={count}` - Search for cryptocurrency news

## Key Components

### Homepage
Displays global cryptocurrency statistics and top 10 cryptocurrencies with latest news.

### Cryptocurrencies
Lists all cryptocurrencies with search functionality. Click on any cryptocurrency to view detailed information.

### CryptoDetails
Shows comprehensive information about a selected cryptocurrency including:
- Current price and market cap
- Supply and circulation data
- Price history chart
- Links to official resources

### News
Displays latest cryptocurrency news from Bing News with filtering by cryptocurrency.

### Exchange
Shows cryptocurrency exchange information and trading volumes.

## Important Notes

- The `.env` file contains your RapidAPI keys. **Never commit this file to version control** with real API keys.
- Some API features (like exchanges) may require a premium RapidAPI plan.
- The app uses React 18's new `createRoot` API for rendering.
- Routes are configured using React Router v6 with `Routes` and `Route` components.
- RTK Query is configured with proper middleware for caching and synchronization.

## Troubleshooting

### API returning 404
- Verify your RapidAPI keys are correct in the `.env` file
- Check that the API endpoints are accessible with your subscription plan
- Ensure the base URLs in `.env` match the current API structure

### Build errors
- Run `npm install` to ensure all dependencies are properly installed
- Clear the node_modules folder and package-lock.json, then reinstall if issues persist
- Check that your Node.js version is compatible (v14+)

### Port already in use
If port 3000 is already in use, you can specify a different port:
```bash
PORT=3001 npm start
```

## Contributing

To modify or extend this project:
1. Update API calls in `src/services/` files
2. Add new components in `src/components/`
3. Update routes in `src/App.js`
4. Modify styles in `src/App.css` or component-specific CSS files

## License

This project is provided as-is for educational and development purposes.

## Support

For issues with the RapidAPI services, visit:
- [CoinRanking API Documentation](https://rapidapi.com/Coinranking/api/coinranking1)
- [Bing News Search API Documentation](https://rapidapi.com/microsoft-azure-org-microsoft-cognitive-services/api/bing-news-search1)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
