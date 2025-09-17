
---

# Personal Finance Management Tool

A full-stack application that helps users manage their personal finances by tracking transactions, creating budgets, and generating financial summaries.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Application Screenshots](#application-screenshots)
- [Technologies Used](#technologies-used)
- [Project Architecture](#project-architecture)
- [Setup Instructions](#setup-instructions)
- [Usage Guidelines](#usage-guidelines)
- [API Endpoints](#api-endpoints)
- [Next Steps](#next-steps)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

The Personal Finance Management Tool is designed to help users track their finances through detailed transaction logs and budgeting features. Users can register, log in, and securely manage their personal financial data. The tool provides an intuitive frontend built with Vue.js, communicating with a backend powered by FastAPI.

---

## Features
- **User Authentication**: JWT-based login and registration.
- **Transaction Management**: Add, edit, view, and delete personal financial transactions.
- **Budget Management**: Create and manage budgets, associate them with transactions.
- **Financial Summary Reports**: Generate a summary report of all transactions.
- **Responsive UI**: The frontend is designed to work seamlessly across devices.

---

## Application Screenshots

### Authentication Pages

#### Login Page
![Login Page](https://github.com/user-attachments/assets/33d36ced-47be-4cc9-b6c5-c2e2753c2abe)

The login page provides a clean and simple interface for user authentication with username and password fields.

#### Registration Page
![Registration Page](https://github.com/user-attachments/assets/77e5c4af-ede0-4b16-8452-8917c2e30464)

The registration page allows new users to create an account with username, full name, email, and password fields.

### Main Application Features

#### Transactions Management
![Transactions Page](https://github.com/user-attachments/assets/f79a9e92-5474-419f-a58c-2e5d5f2a7f48)

The transactions page allows users to:
- Add new transactions with category (Income/Expense), description, amount, and date
- View all transactions in a organized table format
- Edit and delete existing transactions
- Navigate between different sections using the top navigation bar

#### Budget Management
![Budgets Page](https://github.com/user-attachments/assets/9c947841-013a-476b-aae3-1d6362fcb891)

The budgets page enables users to:
- Create new budgets with description, amount, and date range
- View all budgets in a clear layout
- Edit and delete existing budgets

#### Budget Details and Analytics
![Budget Breakdown](https://github.com/user-attachments/assets/df8984f9-26b3-474e-bbe5-9c5f5649cf2e)

When clicking on a budget, users can see detailed analytics including:
- Budget limit amount
- Amount used so far
- Remaining budget
- Usage percentage for better financial tracking

#### Financial Summary Dashboard
![Summary Page](https://github.com/user-attachments/assets/27d4ae76-3f31-4e04-b9f7-7b1c09e72b45)

The summary dashboard provides an overview of:
- Total income
- Total expenses  
- Net savings
- Clear financial overview for informed decision-making

---

## Technologies Used

### Backend:
- **FastAPI**: High-performance, modern API framework.
- **PyMongo**: MongoDB integration for data storage.
- **PyJWT**: Secure authentication using JWT tokens.
- **Passlib**: Password hashing for user security.
- **Pydantic**: Data validation and serialization.

### Frontend:
- **Vue.js**: Progressive JavaScript framework for building user interfaces.
- **Vuetify**: Material Design component framework for Vue.js.
- **Axios**: Promise-based HTTP client for API requests.
- **Vue Router**: Client-side routing.

### Dev Tools:
- **Vite**: Next-generation frontend build tool.
- **ESLint**: Linting tool for identifying and fixing problems in JavaScript code.
- **Prettier**: Code formatting tool for consistent style.

---

## Project Architecture

The project follows a modular architecture with a clear separation of concerns between the frontend and backend.

- **Backend**: 
  - Built using FastAPI with a RESTful API.
  - MongoDB serves as the primary data storage system.
  - JWT-based authentication secures access to the application.
  
- **Frontend**: 
  - Built with Vue.js, utilizing Vuetify for a modern UI.
  - Axios handles HTTP requests to communicate with the backend API.
  - Vue Router provides dynamic navigation between components.

---

## Setup Instructions

### Prerequisites:
- **Python 3.8+** for backend
- **Node.js 16+** for frontend
- **MongoDB** installed or accessible remotely

### Backend Setup (FastAPI)

1. Clone the repository:
   ```bash
   git clone https://github.com/Brendah90/personal-finance-management-tool.git
   cd personal-finance-management-tool/backend
   ```

2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install backend dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up your environment variables in a `.env` file:
   ```bash
   SECRET_KEY=your_jwt_secret_key
   MONGO_URI=mongodb://localhost:27017/your-db-name
   ```

5. Run the FastAPI server:
   ```bash
   uvicorn main:app --reload
   ```

### Frontend Setup (Vue.js)

1. Navigate to the frontend directory:
   ```bash
   cd ../frontend
   ```

2. Install frontend dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Open your browser and navigate to `http://localhost:5173` to view the app.

### Quick Start Guide

Once both backend and frontend servers are running:

1. **Access the Application**: Open `http://localhost:5173` in your web browser
2. **Create an Account**: Click "Register" to create a new user account
3. **Start Adding Transactions**: Navigate to the Transactions page to add your financial data
4. **Set Up Budgets**: Use the Budgets page to create spending limits and track your progress
5. **Monitor Your Finances**: Check the Summary page for an overview of your financial health

> **Note**: Make sure both the backend server (`uvicorn main:app --reload`) and frontend server (`npm run dev`) are running simultaneously for full functionality.

---

## Usage Guidelines

1. **Register a new user**:
   - Go to the registration page and create a new account. You’ll receive a JWT token upon successful registration.
   
2. **Login**:
   - Use your credentials to log in and obtain a JWT token. The token will be required for subsequent API calls to manage transactions and budgets.
   
3. **Managing Transactions**:
   - Add, edit, or delete transactions using the transaction management UI.
   
4. **Setting Budgets**:
   - Create and manage budgets, and associate them with your transactions.
   
5. **Viewing Summary Reports**:
   - Navigate to the reports page to view a summary of all your transactions.

---

## API Endpoints

### Authentication
- `POST /api/v1/auth/register` - Register a new user.
- `POST /api/v1/auth/login` - Log in to the system.

### Transactions
- `GET /api/v1/transactions/` - Retrieve all transactions.
- `POST /api/v1/transactions/` - Add a new transaction.
- `GET /api/v1/transactions/{id}` - Retrieve a specific transaction.
- `PUT /api/v1/transactions/{id}` - Update a transaction.
- `DELETE /api/v1/transactions/{id}` - Delete a transaction.

### Budgets
- `GET /api/v1/budgets/` - Retrieve all budgets.
- `POST /api/v1/budgets/` - Add a new budget.
- `GET /api/v1/budgets/{id}` - Retrieve a specific budget.
- `PUT /api/v1/budgets/{id}` - Update a budget.
- `DELETE /api/v1/budgets/{id}` - Delete a budget.

### Reports
- `GET /api/v1/reports/summary` - Retrieve a summary report of all transactions.

---

## Next Steps

- **Advanced Reporting**: Add visual charts and graphs for financial reports.
- **Role-Based Access Control**: Implement user roles (admin, regular users).
- **Deployment**: Deploy to cloud platforms (e.g., AWS, Heroku, DigitalOcean).

---

## Contributing

If you'd like to contribute, please fork the repository and use a feature branch. Pull requests are warmly welcome.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
