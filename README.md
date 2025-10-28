# Trip Planner API

Trip Planner API is a RESTful microservice system built with Express.js and TypeScript.  
It allows users to plan, manage, and receive recommendations for trips based on their personal preferences.

---

## Overview

The system is divided into multiple independent services:
- **auth** – Handles user registration and authentication.
- **trips** – Manages trip creation, updates, and deletion.
- **activities** – Provides activities based on user interests.
- **locations** – Stores and retrieves location data.
- **offers** – Suggests offers and travel recommendations.
- **reviews** – Manages user reviews and feedback.
- **gateway** – Acts as an API Gateway for routing requests between services.

Each service runs independently and communicates through HTTP requests.

---

## Features

1. **User Registration and Authentication**
   - User account creation and login.
   - JWT-based authentication and authorization.

2. **Profile Management**
   - Retrieve and update user information.
   - Store preferences and travel history.

3. **Trip Management**
   - Create, edit, and delete trips.
   - Retrieve a list of trips for a user.

4. **Recommendations**
   - Suggest destinations, offers, and activities based on user interests.

5. **Personalized Suggestions**
   - Provide trip ideas tailored to user preferences and trip details.

---

## Project Structure

```

src/
├── activities/
├── auth/
├── gateway/
├── locations/
├── offers/
├── trips/
└── reviews/

````

---

## Requirements

- Node.js >= 16  
- TypeScript >= 5.4  
- Express.js >= 4.18  
- PostgreSQL (latest)

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/trip-planner.git
   cd trip-planner
````

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file from `.env.example` and set the required variables:

   ```env
   DB_USER=postgres
   DB_PASS=password
   DB_NAME=tripplanner
   DB_HOST=db
   SECRET_KEY=your_secret_key
   PORT=8000
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Or start all services using Docker Compose:

   ```bash
   docker-compose up --build
   ```

---

## API Endpoints

### Authentication

| Method | Endpoint         | Description                     |
| ------ | ---------------- | ------------------------------- |
| POST   | `/auth/register` | Register a new user             |
| POST   | `/auth/login`    | Log in with an existing account |

### Profile

| Method | Endpoint   | Description                  |
| ------ | ---------- | ---------------------------- |
| GET    | `/profile` | Retrieve profile information |
| PUT    | `/profile` | Update profile details       |

### Trips

| Method | Endpoint     | Description         |
| ------ | ------------ | ------------------- |
| POST   | `/trips`     | Create a new trip   |
| GET    | `/trips`     | Retrieve all trips  |
| PUT    | `/trips/:id` | Update trip details |
| DELETE | `/trips/:id` | Delete a trip       |

### Offers

| Method | Endpoint                             | Description               |
| ------ | ------------------------------------ | ------------------------- |
| GET    | `/offers`                            | Retrieve all offers       |
| GET    | `/offers?price=<value>&type=<value>` | Filter offers by criteria |

### Activities

| Method | Endpoint      | Description                              |
| ------ | ------------- | ---------------------------------------- |
| GET    | `/activities` | Retrieve activities based on preferences |

### Locations

| Method | Endpoint     | Description                                  |
| ------ | ------------ | -------------------------------------------- |
| GET    | `/locations` | Retrieve locations related to user interests |

---

## Docker Services

Each service runs as a separate container managed by Docker Compose.

| Service  | Port | Description                        |
| -------- | ---- | ---------------------------------- |
| gateway  | 8000 | API Gateway                        |
| auth     | 8001 | User authentication service        |
| trip     | 8002 | Trip management service            |
| activity | 8003 | Activity recommendation service    |
| review   | 8005 | Review management service          |
| location | 8006 | Location management service        |
| offer    | 8009 | Offers and recommendations service |
| db       | 5432 | PostgreSQL database                |

---

## Testing

Use [Postman](https://www.postman.com/) or similar tools to test endpoints.
Example commands can be found in the API documentation provided in the repository.

---

## Security

* JWT authentication for protected routes
* Environment variables stored in `.env`
* CORS enabled for client access
* Recommended: use Helmet and rate limiting for production

```

