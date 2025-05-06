# Node.js Backend Starter Template 🚀

This is a simple Node.js backend starter template with a structured file organization, using **Express**, **MongoDB (Mongoose)**, and basic utility functions.

## Table of Contents 📑

* [Project Structure](#project-structure)
* [Setup & Installation](#setup--installation)
* [Environment Variables](#environment-variables)
* [Application Flow](#application-flow)
* [License](#license)

## Project Structure 🗂️

```
├── .envSample              # Sample environment variables file
├── .gitignore              # Git ignore file to exclude node_modules, .env, etc.
├── app.js                  # Main Express app configuration
├── index.js                # Entry point to start the server and connect to DB
├── package-lock.json       # Lock file for dependencies
├── package.json            # Project metadata and dependencies
├── README.md               # Project documentation
│
├── constants               # Directory for constants used across the project
│   └── .gitkeep            # Keeps the directory in git even if empty
│
├── controllers             # Directory for route controllers (business logic)
│   └── .gitkeep            # Keeps the directory in git even if empty
│
├── database                # Directory for database connection
│   └── db.js               # MongoDB connection logic
│
├── middlewares             # Directory for custom middleware functions
│   └── .gitkeep            # Keeps the directory in git even if empty
│
├── models                  # Directory for Mongoose models (database schemas)
│   └── .gitkeep            # Keeps the directory in git even if empty
│
├── routes                  # Directory for route definitions
│   └── .gitkeep            # Keeps the directory in git even if empty
│
└── utils                   # Directory for utility/helper functions
    └── asyncWrapper.js     # Wrapper for async route handlers
```

## Setup & Installation 🛠️

Follow these steps to get your development environment set up and running.

### 1. Clone the repository 📂:

```bash
git clone https://github.com/yourusername/yourrepo.git
cd yourrepo
```

### 2. Install dependencies 📦:

```bash
npm install
```

### 3. Set up environment variables 🌱:

* Copy the `.envSample` file to a new file called `.env`:

```bash
cp .envSample .env
```

* Set your environment variables in the `.env` file:

```
PORT=3000
MONGO_URI=your-mongodb-uri
MONGO_DB=your-database-name
JWT_SECRET=your-jwt-secret
NODE_ENV=development
```

### 4. Run the app 🏃‍♂️:

```bash
npm start
```

The server will start and be available at `http://localhost:3000`.

## Environment Variables 🌍

The following environment variables need to be set in your `.env` file:

* `PORT`: Port for the server to run (e.g., 3000).
* `MONGO_URI`: MongoDB connection URI (e.g., `mongodb://localhost:27017`).
* `MONGO_DB`: The database name to connect to.
* `JWT_SECRET`: A secret string for JWT authentication.
* `NODE_ENV`: Node environment (typically `development` or `production`).

## Application Flow 🔄

1. **index.js**: This is the entry point of the application. It connects to the MongoDB database using the `connectDB()` function from `db.js`. Once the connection is successful, the server starts listening on the specified port.

2. **app.js**: Sets up the Express server with basic middleware to handle JSON requests.

3. **db.js**: Contains the logic for connecting to MongoDB using Mongoose. The `connectDB()` function establishes the connection and handles errors if the connection fails.

4. **asyncWrapper.js**: A utility function that wraps async route handlers to automatically handle errors using `try-catch` blocks. This ensures that errors are passed to the next middleware for proper error handling.

5. **.envSample**: A sample file for storing environment variables, which you can copy to create your own `.env` file.

## License 📝

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
