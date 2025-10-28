# Trip Planner API

Trip Planner API is a RESTful microservice system built with Express.js and TypeScript.  
It provides backend functionality for a trip planning application, including user management, trip creation, and travel recommendations based on user interests.

---

## Overview

Trip Planner is a service assistant for planning travel experiences.  
It supports the following core features:
- User registration and authentication
- Profile creation and management
- Trip creation and modification
- Search among available offers
- Personalized suggestions for new trips based on user interests

---

## Features

1. **User Management**
   - User registration and login with JWT authentication
   - Profile creation and updates

2. **Trip Management**
   - Create, edit, and delete trips
   - Manage trip details (destination, duration, budget, etc.)

3. **Recommendations**
   - Retrieve offers and activities matching user preferences
   - Get personalized trip suggestions

4. **Activities and Locations**
   - Retrieve activities, locations, and offers associated with a user’s interests

5. **Reviews**
   - Manage and view trip or location reviews
   
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

### User

#### Register
**POST** `/v1/register/`  
Registers a new user.

**Request body:**
```json
{
  "email": "dung@gmail.com",
  "name": "Viet Dung",
  "password": "depchai"
}
````

#### Login

**POST** `/v1/login/`
Authenticates a user and returns an access token.

**Request body:**

```json
{
  "email": "truong@gmail.com",
  "password": "depchai"
}
```

**Headers:**

```
Authorization: Bearer <token>
```

---

### Trips

| Method | Endpoint         | Description             |
| ------ | ---------------- | ----------------------- |
| POST   | `/v1/trips/`     | Create a new trip       |
| GET    | `/v1/trips/`     | Retrieve all trips      |
| PUT    | `/v1/trips/:id/` | Update trip information |
| DELETE | `/v1/trips/:id/` | Delete a trip           |

**Example body:**

```json
{
  "title": "Summer in Paris",
  "destination": "France",
  "start_date": "2025-06-10",
  "end_date": "2025-06-20",
  "budget": 1500
}
```

---

### Reviews

| Method | Endpoint           | Description          |
| ------ | ------------------ | -------------------- |
| POST   | `/v1/reviews/`     | Create a new review  |
| GET    | `/v1/reviews/`     | Retrieve all reviews |
| DELETE | `/v1/reviews/:id/` | Delete a review      |

---

### Locations

| Method | Endpoint             | Description               |
| ------ | -------------------- | ------------------------- |
| GET    | `/v1/locations/`     | Retrieve all locations    |
| GET    | `/v1/locations/:id/` | Retrieve location details |

---

### Activities

| Method | Endpoint              | Description               |
| ------ | --------------------- | ------------------------- |
| GET    | `/v1/activities/`     | Retrieve all activities   |
| GET    | `/v1/activities/:id/` | Retrieve activity details |

---

### User Activities (User Interests)

| Method | Endpoint                | Description                          |
| ------ | ----------------------- | ------------------------------------ |
| GET    | `/v1/users-activities/` | Retrieve user’s preferred activities |
| POST   | `/v1/users-activities/` | Add a new activity to user interests |

---

### Trips Locations

| Method | Endpoint               | Description                              |
| ------ | ---------------------- | ---------------------------------------- |
| GET    | `/v1/trips-locations/` | Retrieve locations associated with trips |
| POST   | `/v1/trips-locations/` | Link a location to a trip                |

---

### Locations Activities

| Method | Endpoint                    | Description                             |
| ------ | --------------------------- | --------------------------------------- |
| GET    | `/v1/locations-activities/` | Retrieve activities linked to locations |
| POST   | `/v1/locations-activities/` | Link an activity to a location          |

---

### Offers

| Method | Endpoint                                | Description                    |
| ------ | --------------------------------------- | ------------------------------ |
| GET    | `/v1/offers/`                           | Retrieve all offers            |
| GET    | `/v1/offers?price=<value>&type=<value>` | Filter offers by price or type |

```
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

```

