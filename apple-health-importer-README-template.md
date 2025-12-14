# Apple Health XML Importer

Swift utility for parsing Apple Health XML exports into structured JSON format for analysis and integration.

## Overview

A Swift-based tool that converts Apple Health XML export files into structured JSON format, enabling programmatic analysis, aggregation, and integration with other health tracking systems. The tool provides data transformation, summary statistics, and export capabilities for health data workflows.

## Problem & Motivation

Apple Health exports data in XML format, which is difficult to analyze programmatically and integrate with other tools. Converting to structured JSON enables data analysis, visualization, and integration with databases, analytics platforms, and custom health applications. The tool bridges the gap between Apple's export format and modern data processing workflows.

## Architecture

The system follows a simple transformation pipeline:

1. **XML Parsing**: Read and parse Apple Health XML export file
2. **Data Transformation**: Convert XML elements to structured JSON objects
3. **Aggregation**: Generate summary statistics (daily steps, heart rate averages, workout summaries)
4. **Export**: Output JSON files for downstream processing

The tool is designed as a command-line utility with optional GUI wrapper, supporting batch processing of multiple export files.

## Key Technical Decisions

- **Swift Native**: Chose Swift for native macOS/iOS compatibility and efficient XML parsing
- **JSON Output**: Structured JSON format enables easy integration with Python, JavaScript, and other ecosystems
- **Aggregation Logic**: Built-in summaries reduce need for post-processing
- **Modular Design**: Separated parsing, transformation, and export logic for extensibility

## Setup & Usage

### Installation

```bash
# Clone repository
git clone <GITHUB_LINK_OTHER>
cd apple-health-importer

# Build
swift build

# Run
swift run
```

### Command Line

```bash
# Basic conversion
./apple-health-importer export.xml output.json

# With aggregation
./apple-health-importer export.xml output.json --aggregate

# Batch processing
./apple-health-importer *.xml --output-dir json_exports/
```

### Swift API

```swift
import AppleHealthImporter

let parser = HealthXMLParser()
let data = try parser.parse(filePath: "export.xml")
let json = try data.toJSON()
try json.write(to: URL(fileURLWithPath: "output.json"))

// Aggregation
let summary = data.aggregate()
print(summary.dailySteps)
print(summary.heartRateAverage)
```

## Results / Metrics

- **Data Transformation**: Successfully converts Apple Health XML to structured JSON
- **Aggregation**: Generates useful summary statistics for common health metrics
- **Integration**: JSON output enables integration with analytics tools and databases
- **Performance**: Efficient parsing handles large export files

## Limitations

- Limited to Apple Health export format (may not support other health data formats)
- Aggregation logic covers common metrics but may not handle all data types
- No real-time sync or incremental updates (requires full export each time)
- macOS/iOS focused (may require adaptation for cross-platform use)

## Roadmap

- Add support for incremental updates and delta exports
- Expand aggregation to cover additional health metrics and data types
- Develop Python/JavaScript wrappers for cross-platform usage
- Add data visualization and reporting features
- Integrate with health analytics platforms (Fitbit, Google Fit)
- Add data validation and quality checks
- Develop GUI application for non-technical users

## Links

- **GitHub**: <GITHUB_LINK_OTHER>
- **Documentation**: See `docs/` for usage examples and API reference
