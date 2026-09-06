# reCAPTCHA v3 Solver - Integration Guide

## Quick Setup
```bash
git clone https://github.com/hikaru-saito-dev/recapthca-v3.git
cd recapthca-v3
npm install
npx playwright install chromium
node index.js
```

## How It Works
```
Request -> Playwright Browser -> Load Page -> Solve reCAPTCHA -> Return Token
```

## Troubleshooting
| Issue | Fix |
|-------|-----|
| Browser won't launch | Run npx playwright install |
| Token rejected | Check site key matches domain |
| Timeout | Increase timeout in config |
| Rate limited | Add delay between requests |

## Docker
```dockerfile
FROM mcr.microsoft.com/playwright:v1.40.0
WORKDIR /app
COPY . .
RUN npm ci
CMD ["node", "index.js"]
```