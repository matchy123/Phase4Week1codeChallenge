# Superheroes API Project

This project involves creating a Flask API for a superheroes application, with a React frontend to interact with the API. The goal is to build out the API functionality to manage heroes and their powers, utilizing a pre-existing React frontend for testing.

## Project Setup

### Requirements

- Flask for the backend API
- React for the frontend application
- Pipenv for Python package management
- NPM for JavaScript package management

### Installation

1. Clone the repository to your local machine.

2. Install backend dependencies with Pipenv:
   ```
   pipenv install
   ```
3. Install frontend dependencies with NPM:
   ```
   npm install --prefix client
   ```

### Running the Applications

- To start the Flask API, run:
  ```
  python app.py
  ```
  This will serve the API on `localhost:5555`.

- To start the React frontend application, run:
  ```
  npm start --prefix client
  ```
  This will serve the frontend on `localhost:4000`.

### Testing

- Use `pytest -x` to run the included tests and check the implementation.
- Alternatively, interact with the API through the frontend or Postman to test functionality.

## Models and Relationships

- **Hero** has many **Powers** through **HeroPower**.
- **Power** has many **Heroes** through **HeroPower**.
- **HeroPower** belongs to both **Hero** and **Power**.

Refer to the provided domain diagram for table structures and relationships. After defining models and migrations, seed the database to create initial data for testing.

## Validations

- **HeroPower**: `strength` must be either 'Strong', 'Weak', or 'Average'.
- **Power**: `description` must be present and at least 20 characters long.

## API Endpoints

### GET `/heroes`

Returns a list of heroes with their IDs, names, and super names.

### GET `/heroes/:id`

Returns details of a specific hero, including their powers, if the hero exists. Otherwise, returns an error message with an appropriate HTTP status code.

### GET `/powers`

Returns a list of powers with their IDs, names, and descriptions.

### GET `/powers/:id`

Returns details of a specific power if it exists. Otherwise, returns an error message with an appropriate HTTP status code.

### PATCH `/powers/:id`

Updates an existing power's description if the power exists and the new description passes validations. Returns the updated power or an error message as appropriate.

### POST `/hero_powers`

Creates a new association between a hero and a power with specified strength. Returns details of the associated hero if successful, or an error message if not.

## Deployment

This project is set up for local development. For deployment, configure the Flask app for production with a WSGI server like Gunicorn and serve the React app from a static file server or integrate with Flask.

## Testing and Development

The project includes tests for backend functionality. During development, use these tests, the React frontend, or tools like Postman to interact with and test the API. 

Remember, the focus is on completing the Flask API according to the specifications; the React frontend is provided for testing purposes and does not require modifications.
