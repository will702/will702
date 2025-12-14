# NutriCart

Nutrition-aware grocery optimization app that recommends products based on dietary goals and budget constraints.

## Overview

NutriCart is a full-stack application that helps users optimize grocery shopping by balancing nutrition, budget, and dietary preferences. The system includes a lightweight recommendation engine, cart optimization logic, and API backend supporting frontend integration. Built as a functional prototype during a Product & UX hackathon, demonstrating end-to-end ML and backend development capabilities.

## Problem & Motivation

Grocery shopping lacks intelligent optimization that considers both nutritional value and budget constraints. Users struggle to balance health goals with cost efficiency, leading to suboptimal choices. Automated recommendation systems can help users make informed decisions while staying within budget and meeting dietary requirements.

## Architecture

The system consists of three main components:

1. **Backend API**: FastAPI-based service providing product data, nutrition scoring, and recommendation endpoints
2. **Recommendation Engine**: Lightweight ML system that scores products based on nutrient profiles, budget, and user preferences
3. **Frontend**: React-based UI for product browsing, cart management, and optimization visualization

Data flows from product database → nutrition scoring → recommendation algorithm → API endpoints → frontend display → cart optimization.

## Key Technical Decisions

- **FastAPI Backend**: Chose FastAPI for rapid development, automatic API documentation, and async support
- **Lightweight ML**: Implemented scoring-based recommendation system suitable for real-time inference
- **Modular Design**: Separated recommendation logic from API layer for easy experimentation
- **Prototype-First**: Prioritized functional demo over production-scale features to validate concept

## Setup & Usage

### Backend

```bash
# Install dependencies
pip install fastapi uvicorn pandas numpy

# Run API server
uvicorn main:app --reload
```

### Frontend

```bash
# Install dependencies
npm install

# Run development server
npm start
```

### API Endpoints

```python
# Get product recommendations
GET /api/recommendations?budget=100000&dietary_prefs=vegetarian

# Score product nutrition
POST /api/score
{
  "product_id": "123",
  "nutrition_data": {...}
}

# Optimize cart
POST /api/optimize-cart
{
  "items": [...],
  "budget": 100000
}
```

## Results / Metrics

- **Functional Prototype**: Delivered working demo with recommendation and cart optimization
- **API Integration**: Successfully supported frontend with real-time data flows
- **Hackathon Completion**: Functional prototype + UX demo delivered within time constraints
- **Modular Architecture**: Codebase supports extension to production-scale features

## Limitations

- Product database limited to prototype data
- Recommendation algorithm is lightweight and may not scale to large catalogs
- No user authentication or personalized preferences
- Budget optimization is simplified and may not handle complex constraints
- No integration with actual grocery store APIs or inventory systems

## Roadmap

- Expand product database with real grocery store data and nutrition information
- Implement collaborative filtering and personalized recommendation algorithms
- Add user accounts and preference learning over time
- Integrate with grocery store APIs for real-time pricing and availability
- Develop mobile app version for on-the-go shopping
- Add meal planning features and recipe integration
- Implement budget tracking and spending analytics

## Links

- **GitHub**: <GITHUB_LINK_NUTRICART>
- **API Documentation**: Available at `/docs` when running FastAPI server
