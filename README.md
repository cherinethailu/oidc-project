# Capital Bank - OIDC Banking Application

A comprehensive banking application that integrates with Fayda for secure identity verification and provides a complete banking dashboard experience.

## Features

- Secure authentication via Fayda integration
- Professional banking dashboard
- Account verification status tracking
- Loan eligibility checker
- Account balance overview
- Transaction history with filtering
- Exchange rates with currency converter
- User profile management with KYC fields
- Session-based authentication with logout functionality

## Prerequisites

- Python 3.11 or higher
- Git

## Installation and Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd oidc_project
```

### 2. Create Virtual Environment

**Linux/Mac:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Database Setup

Run the following command to create and apply database migrations:

```bash
python manage.py migrate
```

### 5. Environment Configuration

Create a `.env` file in the project root with the following variables:

```env
CLIENT_ID=your_client_id
REDIRECT_URI=http://localhost:3000/callback/
AUTHORIZATION_ENDPOINT=your_authorization_endpoint
TOKEN_ENDPOINT=your_token_endpoint
USERINFO_ENDPOINT=your_userinfo_endpoint
PRIVATE_KEY=your_private_key
ALGORITHM=RS256
CLIENT_ASSERTION_TYPE=urn:ietf:params:oauth:client-assertion-type:jwt-bearer
```

## Running the Application

### Start the Development Server

```bash
python manage.py runserver 3000
```

The application will be available at `http://localhost:3000`

### Port Configuration

- **Default Port:** 3000
- **Callback URL:** `http://localhost:3000/callback/`
- **Redirect URI:** Must match the REDIRECT_URI in your .env file

If you need to change the port, update the REDIRECT_URI in your .env file accordingly.

## Usage

### 1. Access the Application

Open your web browser and navigate to `http://localhost:3000`

### 2. Authentication Flow

1. Click "Sign in with Fayda" on the home page
2. You will be redirected to the Fayda authentication system
3. Complete the authentication process
4. You will be redirected back to the application with your verified identity
5. Access the banking dashboard with your authenticated session

### 3. Banking Features

Once authenticated, you can access:

- **Dashboard:** Overview of all banking features
- **Profile Management:** Update personal information and KYC details
- **Account Verification:** Check verification status
- **Loan Eligibility:** Check loan options and eligibility
- **Account Balance:** View account balances
- **Transactions:** Review transaction history
- **Exchange Rates:** View currency exchange rates

### 4. Logout

Click the "Logout" button in the header to end your session and return to the home page.

## Project Structure

```
oidc_project/
├── oidc_app/
│   ├── templates/oidc_app/
│   │   ├── home.html
│   │   ├── callback.html
│   │   ├── dashboard.html
│   │   ├── profile.html
│   │   ├── account_verification.html
│   │   ├── loan_eligibility.html
│   │   ├── account_balance.html
│   │   ├── transactions.html
│   │   └── exchange_rates.html
│   ├── views.py
│   ├── urls.py
│   └── models.py
├── oidc_project/
│   ├── settings.py
│   └── urls.py
├── manage.py
└── requirements.txt
```

## Technical Details

- **Framework:** Django 5.1
- **Authentication:** OIDC with Fayda
- **Database:** SQLite (development)
- **Session Management:** Django sessions
- **Frontend:** HTML5, CSS3, JavaScript
- **Icons:** Font Awesome 6.0

## Troubleshooting

### Common Issues

1. **Port Already in Use:**
   - Change the port: `python manage.py runserver 8000`
   - Update REDIRECT_URI in .env file accordingly

2. **Database Errors:**
   - Run migrations: `python manage.py migrate`

3. **Environment Variables:**
   - Ensure all required variables are set in .env file
   - Check that REDIRECT_URI matches your server configuration

4. **Authentication Issues:**
   - Verify Fayda endpoints are accessible
   - Check client credentials and private key format

## Security Notes

- This application uses session-based authentication
- User data is stored in Django sessions
- All OIDC communications are secured with JWT tokens
- Private keys should be kept secure and not committed to version control

## Support

For technical support or questions about the application, please refer to the Django documentation or contact the development team.