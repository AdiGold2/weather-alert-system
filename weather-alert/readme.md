# 🌦️ Weather Alert System

A full-stack weather alert application built with **Spring Boot** and **React**.  
It fetches real-time weather data from the [Tomorrow.io API](https://www.tomorrow.io/) and allows users to define custom alerts that are evaluated periodically.

---

## 🚀 Features

### 🔧 Backend (Spring Boot)
- Integrates with Tomorrow.io API to fetch live weather data
- REST API to:
  - Create new weather alerts
  - List all existing alerts
- Scheduled service to evaluate alerts every 5 minutes
- Uses H2 in-memory database for easy setup
- Handles rate-limiting and duplicate API requests via caching

### 🎨 Frontend (React)
- Live weather display for any city
- Create new weather alerts via a styled form
- View list of all alerts and see which are currently triggered
- Built with `styled-components` for modular, responsive styling

---

## ⚙️ Technologies Used

| Layer     | Tech Stack                                   |
|-----------|-----------------------------------------------|
| Frontend  | React, Axios, styled-components               |
| Backend   | Java 17, Spring Boot, Spring Scheduler, RestTemplate |
| Database  | H2 (in-memory)                                |
| API       | Tomorrow.io                                   |

---

## 🛠️ How It Works

1. User opens the app and views live weather data
2. User creates alerts like:
   - Temperature > 30°C
   - Wind Speed < 10 km/h
3. Every 5 minutes, the backend:
   - Fetches updated weather data
   - Evaluates all alerts
   - Marks `triggered: true` for matching ones
4. Alerts appear with ✅ or 🚨 in the frontend

---

## 🔧 Setup Instructions

### 🔹 Prerequisites

- [Node.js](https://nodejs.org/en/) + npm
- Java 17
- Maven
- Tomorrow.io API key (free tier is sufficient)

---

### 🖥️ Backend Setup (Spring Boot)

```bash
cd weather-alert

# Copy and configure your API key
cp src/main/resources/application.properties.example src/main/resources/application.properties
# Edit the file and add your Tomorrow.io API key

# Build and run the app
mvn clean install
mvn spring-boot:run

### 🌐 Frontend Setup (React)
cd weather-alert-frontend
npm install
npm start
