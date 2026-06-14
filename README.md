# DEX Trading Volume Analytics(Last 30 Days)

## Overview
Analysis of decentralized exchange (DEX) trading volume over a 30-day period using live on-chain blockchain data.

## Tools Used
- **Dune Analytics** : SQL queries on live blockchain data
- **Microsoft Power BI** : Data visualization and dashboard

## Key Findings
- Total DEX trading volume: $151.17 billion
- Peak single-day volume reached $9.5 billion
- The highest single day trading volume was recorded in June

## SQL Query
```sql
SELECT date_trunc('day', block_time) AS Date, 
       SUM(amount_usd) AS total_dollar_volume
FROM dex.trades 
WHERE block_time >= now() - interval '30' day 
GROUP BY date_trunc('day', block_time)
ORDER BY date_trunc('day', block_time)
```

## Dashboard
<img width="967" height="543" alt="image" src="https://github.com/user-attachments/assets/6c256a52-1720-4ecc-93fa-41f451e379a4" />

