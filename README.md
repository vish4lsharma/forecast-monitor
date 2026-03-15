# Forecast Monitoring Web Application

Production-ready dashboard for monitoring and analyzing UK Wind Generation vs Forecasts using BMRS Elexon API.

![Dashboard Preview](./dashboard.png)

## Architecture

- **Frontend**: Next.js (App Router), TailwindCSS, Recharts, Lucide React.
- **Backend (Serverless)**: Next.js API Routes (Integrated into the frontend for seamless Vercel hosting).
- **Data Source**: BMRS Elexon API v1 (FUELHH for actuals, WINDFOR for forecasts).

## Project Structure

```text
/forecast-monitor-app
    /frontend        - Next.js Web App (including API routes)
    /backend         - Legacy Express API Server (Optional)
    /analysis        - Jupyter Notebook for Wind Data Analysis
```

## Features

- **Dynamic Forecasting**: Select "Forecast Horizon" (0-48h) to see historical forecast accuracy.
- **Merged View**: Automatically aligns actual and forecast values by Target Time (UTC).
- **Interactive Charts**: Line charts comparing Actual (Blue) vs Forecast (Green).
- **Data Range Selection**: Filter January 2024 data by start and end times.
- **Error Analysis**: Built-in metrics for average generation.

## Setup Instructions

### Local Development

1. Navigate to the `frontend` directory.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```
4. The dashboard runs on `http://localhost:3000`.

## Deployment

### Vercel (Recommended)

1. Connect your Github repository to [Vercel](https://vercel.com).
2. Set the **Root Directory** to `frontend`.
3. Vercel will automatically detect Next.js and deploy both the UI and the API Routes.
4. No additional environment variables are strictly required for the public BMRS API, but you can set `NODE_ENV` if needed.

## AI Tools Used

- **Antigravity AI (Google Deepmind)**: For code generation, architectural design, and documentation.

## Analysis Notebook

The `/analysis/wind_analysis.ipynb` contains:
- **Forecast Error Analysis**: MAE, Median, P99, error correlation with horizon/time.
- **Wind Reliability Analysis**: Percentile generation, minimum dependable capacity.

