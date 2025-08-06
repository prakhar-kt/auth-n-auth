# FastAPI Authentication & Authorization

A comprehensive FastAPI application demonstrating modern authentication and authorization patterns with JWT tokens, refresh tokens, and role-based access control.

## Features

- **User Registration & Login** - Secure user account creation and authentication
- **JWT Authentication** - Access tokens with automatic expiration
- **Refresh Tokens** - Long-lived tokens stored as HTTP-only cookies
- **Password Security** - Bcrypt hashing with salt
- **Email Verification** - Token-based email confirmation
- **Password Reset** - Secure password reset flow via email tokens
- **Role-Based Access** - Admin and user role management
- **Session Management** - Token revocation and logout functionality

## Quick Start

### Prerequisites
- Python 3.11+
- uv package manager

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd auth-n-auth

# Install dependencies
uv sync

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration
```

### Environment Variables

Create a `.env` file with:

```env
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
DATABASE_URL=sqlite:///./app.db
```

### Running the Application

```bash
# Start the development server
uv run fastapi dev app/main.py

# The API will be available at http://localhost:8000
# Documentation at http://localhost:8000/docs
```

## API Endpoints

### Authentication
- `POST /account/register` - Create new user account
- `POST /account/login` - User login with credentials
- `POST /account/refresh` - Refresh access token
- `POST /account/logout` - Revoke refresh token and logout

### User Management
- `GET /account/me` - Get current user profile
- `POST /account/change-password` - Change user password
- `POST /account/verify-request` - Request email verification
- `GET /account/verify` - Verify email with token

### Password Recovery
- `POST /account/forgot-password` - Request password reset
- `POST /account/reset-password` - Reset password with token

### Admin
- `GET /account/admin` - Admin-only endpoint

## Security Features

- **Password Hashing** - Bcrypt with automatic salt generation
- **JWT Tokens** - Short-lived access tokens (15 minutes)
- **Secure Cookies** - HTTP-only refresh tokens (7 days)
- **Token Validation** - Comprehensive token verification
- **Role-Based Access** - Admin and user permission levels

## Tech Stack

- **FastAPI** - Modern Python web framework
- **SQLModel** - Database ORM with type hints
- **Passlib** - Password hashing utilities
- **Python-JOSE** - JWT token handling
- **Python-Decouple** - Environment configuration
- **uv** - Fast Python package manager

## Development

```bash
# Run in development mode
uv run fastapi dev app/main.py

# Add new dependencies
uv add package-name

# Remove dependencies
uv remove package-name
```

## License

MIT License
