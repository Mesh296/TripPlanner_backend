# Trip Planner API

**Trip Planner API** is a RESTful service built with Express.js and TypeScript. The application supports users in planning trips, from registration and trip creation to searching for recommendations based on personal preferences.

## Key Features

1. **User Registration and Authentication**
   - Supports account creation and user authentication.

2. **Profile Management**
   - Users can create and update their personal information, including preferences and activity history.

3. **Trip Creation and Management**
   - Create new trips with detailed information.
   - Update or delete previously created trips.

4. **Travel Recommendations**
   - Based on personal interests, the system suggests destinations or activities that match user preferences.

5. **Personalized Suggestions for New Trips**
   - Provides tailored suggestions for newly created trips based on user preferences and trip information.

## Project Structure

The project follows a standard folder structure for source code management:

```
src/
├── controllers/
├── models/
├── middlewares/
├── routes/
├── services/
└── utils/
```

## Requirements

- **Node.js** >= 16
- **TypeScript** >= 5.4
- **Express.js** >= 4.18
- **PostgreSQL**

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/trip-planner.git
   cd trip-planner
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure the database and environment variables:
   - Create a `.env` file from `.env.example` and fill in the necessary details.

4. Start the server:
   ```bash
   npm run dev
   ```

## Usage

### User Registration and Authentication

- **POST** `/auth/register` - Register a new account.
- **POST** `/auth/login` - Log in with an existing account.

### Profile Management

- **GET** `/profile` - View profile information.
- **PUT** `/profile` - Update profile details.

### Trip Management

- **POST** `/trips` - Create a new trip.
- **GET** `/trips` - Retrieve a list of trips.
- **PUT** `/trips/:id` - Update trip details.
- **DELETE** `/trips/:id` - Delete a trip.

### Recommendations

- **GET** `/offers` - Retrieve all travel suggestions.
- **GET** `/offers?price=<value>&type=<value>` - Search for suggestions based on criteria.

### Interest-Based Suggestions

- **GET** `/activities` - Retrieve a list of activities that match user preferences.
- **GET** `/locations` - Find locations related to user interests.

## Testing

Use [Postman](https://www.postman.com/) or a similar tool to test the API. Sample endpoints have been tested and documentation is included in the repository.

## Contributions

If you would like to contribute to the project, please submit a pull request or create an issue on GitHub.
