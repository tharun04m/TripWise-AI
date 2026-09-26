# TripWise AI

## Overview

TripWise AI is an India-focused budget travel recommendation and itinerary planning application. It helps users find suitable travel destinations based on their budget, trip duration, travel style, transportation preferences, and accommodation preferences.

The application is developed using FastAPI, SQLAlchemy, and React/Vite. It provides destination recommendations, estimated travel costs, and rule-based day-wise itineraries.

## Objectives

* Recommend destinations according to user preferences.
* Provide estimated travel expenses.
* Generate day-wise travel itineraries.
* Provide an easy-to-use travel planning interface.
* Store and manage destination information.

## Technologies Used

* Python
* FastAPI
* React
* Vite
* JavaScript
* SQLAlchemy
* SQLite
* MySQL

## Features

* Budget-based destination recommendations
* Travel-style based recommendations
* Duration-based recommendations
* Transport preference selection
* Accommodation preference selection
* Transportation cost estimation
* Accommodation cost estimation
* Food cost estimation
* Activity cost estimation
* Day-wise itinerary generation
* REST API
* Interactive API documentation
* Database integration

The recommendation system considers budget, duration, travel style, transport, and stay preferences. It also provides estimates for transportation, accommodation, food, activities, and miscellaneous expenses.

## Installation

Create a virtual environment:

```powershell
python -m venv .venv
```

Activate the virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the required dependencies:

```powershell
pip install -r backend\requirements.txt
```

Create the environment configuration file:

```powershell
Copy-Item .env.example .env
```

The application uses SQLite by default:

```text
DATABASE_URL=sqlite:///./tripwise.db
FRONTEND_ORIGIN=http://localhost:5173
```

MySQL can also be configured using the `DATABASE_URL` variable.

## Running the Application

### Backend

Start the FastAPI server:

```powershell
uvicorn app.main:app --app-dir backend --reload
```

The backend normally runs at:

```text
http://127.0.0.1:8000
```

FastAPI documentation is available at:

```text
http://127.0.0.1:8000/docs
```

### Frontend

Open another terminal and run:

```powershell
cd frontend
npm install
npm run dev
```

The frontend normally runs at:

```text
http://localhost:5173
```

The project uses FastAPI for the backend and React/Vite for the frontend.

## Recommendation System

TripWise AI uses a rule-based recommendation scoring system:

* Budget Fit: 50%
* Travel Style Match: 30%
* Duration Suitability: 20%

This scoring helps match destinations with the user's travel requirements.

## Itinerary Generation

The application generates a rule-based day-wise itinerary based on the selected destination and trip duration.

The itinerary generation does not require a paid AI API.

## Cost Estimation

The application provides estimated costs for:

* Transportation
* Accommodation
* Food
* Activities
* Miscellaneous expenses

These estimates help users understand the approximate budget required for their trip.

## Database

SQLite is used as the default database, allowing the application to run without requiring a separate database server.

MySQL is also supported for production-style deployment.

To populate the database:

```powershell
python scripts\seed_database.py
```

## API Documentation

FastAPI provides interactive API documentation at:

```text
http://127.0.0.1:8000/docs
```

This allows developers to view and test the available REST APIs.

## Important Note

The destinations, costs, activities, and travel suggestions are curated sample estimates. They do not represent live prices, availability, bookings, schedules, or safety information.

## Future Scope

* Integration with live travel APIs
* Real-time hotel and transportation prices
* Online booking integration
* Weather-based recommendations
* User authentication
* Personalized recommendations
* Mobile application
* Maps and navigation integration

## Project Summary

TripWise AI is a full-stack travel recommendation and itinerary planning application developed using **Python, FastAPI, React, Vite, SQLAlchemy, and SQLite/MySQL**.

It demonstrates the integration of frontend development, backend REST APIs, database management, and recommendation logic into a travel-planning application.

## License

This project is developed for academic and educational purposes.
