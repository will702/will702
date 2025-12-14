# UW-Tracker

Analytics platform for IPO underwriter performance in Indonesian capital markets, available as web platform and mobile app.

## Overview

UW-Tracker provides comprehensive analytics on IPO underwriter performance, including searchable databases, benchmark scoring, historical statistics, and automated data enrichment. The platform combines web and mobile interfaces, with the mobile app published to Google Play Store. Built during a FinTech/Algo-Trading hackathon and completed as an MVP within time constraints.

## Problem & Motivation

IPO underwriter data in Indonesian markets is fragmented across multiple sources, making it difficult for investors and analysts to compare performance, track historical trends, and make informed decisions. Manual data collection is time-consuming and error-prone, limiting accessibility to quantitative insights.

## Architecture

The system follows a three-tier architecture:

1. **Data Layer**: Automated ETL pipeline using Python scraper, Airtable for data storage, and Make.com for workflow automation
2. **Backend**: Node.js/Express APIs serving underwriter data, scoring algorithms, and historical analytics
3. **Frontend**: Next.js web platform with search, filtering, and charts; React Native mobile app with on-device processing and dashboards

Data flows from web scraping → Airtable normalization → Make.com enrichment (Telegram + LLM) → API layer → web/mobile clients.

## Key Technical Decisions

- **Airtable Integration**: Chose Airtable for rapid schema iteration and human-in-the-loop data validation
- **Make.com Automation**: Automated data refresh and enrichment workflows to reduce manual maintenance
- **Dual Platform Strategy**: Web for comprehensive analytics, mobile for quick reference and on-the-go access
- **On-Device Processing**: Mobile app processes data locally to reduce API calls and improve responsiveness
- **Rapid Deployment**: Shipped to Play Store within 48 hours using React Native and Vercel for web hosting

## Setup & Usage

### Web Platform

```bash
# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
# Set Airtable API keys, Make.com webhooks

# Run development server
npm run dev
```

### Mobile App

```bash
# React Native setup
cd mobile
npm install
npx react-native run-android

# Build for production
cd android && ./gradlew assembleRelease
```

### Data Pipeline

```bash
# Run scraper
python scraper/ihsg_scraper.py

# Trigger Make.com workflow
# Configure Airtable sync and Telegram notifications
```

## Results / Metrics

- **Time to Market**: Mobile app published to Google Play Store within 48 hours
- **Data Coverage**: Automated tracking of Indonesian IPO underwriter performance
- **User Access**: Publicly available on Play Store with graphical UI updates
- **Automation**: Reduced manual data collection from hours to automated refresh cycles

## Limitations

- Data scope limited to Indonesian capital markets (IHSG)
- Scraper requires maintenance as source websites change structure
- Mobile app features subset of web platform capabilities
- LLM enrichment may introduce inconsistencies requiring validation

## Roadmap

- Expand coverage to additional Southeast Asian markets
- Implement real-time alerts for new IPO filings and performance updates
- Add comparative analytics and peer benchmarking features
- Develop API for third-party integrations
- Enhance mobile app with offline caching and push notifications
- Build admin dashboard for data quality monitoring

## Links

- **GitHub**: <GITHUB_LINK_UW_TRACKER>
- **Play Store**: https://play.google.com/store/apps/details?id=com.will702.uwtrackermobile
- **Web Platform**: [Deployment URL]
