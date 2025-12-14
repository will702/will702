# IHSG Underwriter Scraper

Automated ETL pipeline for collecting and normalizing IPO underwriter data from Indonesian capital markets.

## Overview

A Python-based web scraper that automates collection of IPO underwriter data from Indonesian Stock Exchange (IHSG) sources. The system performs data extraction, normalization, and JSON output generation, integrated into the UW-Tracker analytics platform and personal data stack. Built during a Data Engineering sprint as a fully working ETL automation.

## Problem & Motivation

IPO underwriter data is scattered across multiple websites and requires manual collection, making it time-consuming and error-prone. Automated scraping enables regular data refresh, reduces manual effort, and ensures consistency for downstream analytics applications. The scraper serves as a foundational component for quantitative analysis of Indonesian capital markets.

## Architecture

The scraper follows a standard ETL pattern:

1. **Extract**: Web scraping using Python libraries to fetch HTML content from target sources
2. **Transform**: Data parsing, cleaning, and normalization to structured format
3. **Load**: JSON output generation for integration with analytics platforms (Airtable, UW-Tracker)

The system is designed for scheduled execution (cron jobs, Make.com workflows) and handles common web scraping challenges (rate limiting, HTML structure changes, error handling).

## Key Technical Decisions

- **Python Ecosystem**: Leveraged requests, BeautifulSoup, and pandas for robust scraping and data processing
- **JSON Output**: Chose JSON for easy integration with downstream systems (Airtable, APIs, databases)
- **Modular Design**: Separated scraping, parsing, and normalization logic for maintainability
- **Error Handling**: Implemented retry logic and graceful degradation for unreliable sources
- **Integration-Ready**: Designed for seamless integration with UW-Tracker and automation platforms

## Setup & Usage

### Installation

```bash
pip install requests beautifulsoup4 pandas lxml
```

### Basic Usage

```python
from scraper import IHSGUnderwriterScraper

# Initialize scraper
scraper = IHSGUnderwriterScraper()

# Run extraction
data = scraper.scrape()

# Normalize and export
normalized = scraper.normalize(data)
scraper.export_json(normalized, 'output/underwriters.json')
```

### Command Line

```bash
# Run scraper
python scraper/ihsg_scraper.py

# Output to file
python scraper/ihsg_scraper.py --output data/underwriters.json

# Schedule with cron
0 9 * * * cd /path/to/scraper && python ihsg_scraper.py
```

### Integration with Make.com

```bash
# Configure webhook or scheduled trigger
# Scraper outputs JSON → Make.com workflow → Airtable update
```

## Results / Metrics

- **Automation**: Eliminated manual data collection, reducing effort from hours to automated execution
- **Data Quality**: Consistent JSON output enables reliable downstream processing
- **Integration**: Successfully integrated into UW-Tracker platform and analytics stack
- **Reliability**: Handles common web scraping challenges with error recovery

## Limitations

- Scraper requires maintenance as source websites change HTML structure
- Rate limiting may slow down data collection from target sources
- No real-time monitoring or alerting for scraping failures
- Data validation is basic and may miss edge cases
- Limited to Indonesian Stock Exchange (IHSG) sources

## Roadmap

- Add monitoring and alerting for scraping failures
- Implement more robust error handling and retry strategies
- Expand to additional data sources (regional exchanges, financial news)
- Add data validation and quality checks
- Develop API wrapper for programmatic access
- Add historical data backfill capabilities
- Implement incremental updates to reduce redundant scraping

## Links

- **GitHub**: <GITHUB_LINK_SCRAPER>
- **Integration**: Used by [UW-Tracker](GITHUB_LINK_UW_TRACKER)
