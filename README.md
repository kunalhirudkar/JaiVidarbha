# Jai Vidarbha Party - Enterprise Application

A comprehensive Flutter-based enterprise platform for political party management, member engagement, and community outreach.

## Features

### 1. User Management
- User Registration & Authentication (OTP-based)
- Role-based Access Control (President, Vice President, Speaker, Chairperson, etc.)
- Hierarchical organization (Village → Taluka → District → Division)
- Profile management with interests and profession tracking

### 2. Member Management
- Add and manage party members
- Hierarchical structure management
- Referral system with history tracking
- Member status tracking (Joining, Active, Inactive)

### 3. Donation System
- Multiple payment options (RuPay, Credit Card, Debit Card, UPI/BHIM)
- Payment history and tracking
- Banking partner integration
- Donation status monitoring

### 4. Issue Management & Communication
- Party Inside Issues
- Party Outside Issues
- Women-specific issue reporting (Report Issue For Ladies Only)
- Level-based communication (Designated people only)
- Issue category management

### 5. Event Management
- Event poster creation and sharing
- Personal event portfolio
- Calendar management (Monthly view)
- Event details tracking (Birthdays, Anniversaries, Protests, Meetings)
- Event type categorization

### 6. Social Media Integration
- Link Facebook, Twitter, Instagram accounts
- Create and schedule event posters
- Social media news feed (Party-related content)
- Content management with multi-language support

### 7. Task Management
- Profile setup tasks
- Social media linking tasks
- Member collection tasks
- Event organization tasks
- Progress tracking

### 8. Content Management
- Multi-language support (English, Marathi, Hindi)
- Data privacy policy management
- Photo upload with criteria
- Poster creation and management

## Architecture

```
Jai Vidarbha Platform
├── Flutter Mobile App (Frontend)
├── API Gateway (Routing & Authentication)
├── Microservices
│   ├── Auth Service
│   ├── User Profile Service
│   ├── Member Management Service
│   ├── Donation Service
│   ├── Issue Management Service
│   ├── Event Management Service
│   ├── Social Media Service
│   ├── Communication Service
│   └── Content Management Service
├── Database Layer
└── External Integrations (RuPay, SMS Gateway, etc.)
```

## Project Structure

See [ARCHITECTURE.md](docs/ARCHITECTURE.md) for detailed architecture documentation.
See [API_SPECIFICATION.md](docs/API_SPECIFICATION.md) for API endpoints.

## Tech Stack

### Frontend
- **Flutter 3.x** - Cross-platform mobile development
- **State Management** - Riverpod/Provider
- **Local Storage** - Hive/SQLite

### Backend
- **API Gateway** - Node.js/Express or Go
- **Microservices** - Node.js/Express, Python/FastAPI, or Go
- **Database** - PostgreSQL
- **Message Queue** - RabbitMQ/Redis
- **Real-time Communication** - WebSockets/Firebase

### External Services
- **Payment** - RuPay API
- **SMS** - Twilio/AWS SNS
- **Email** - SendGrid
- **Social Media** - Facebook/Twitter/Instagram APIs

## Getting Started

See [SETUP.md](docs/SETUP.md) for development setup instructions.

## Contributing

Please read [CONTRIBUTING.md](docs/CONTRIBUTING.md) for contribution guidelines.

## License

MIT License - See LICENSE file for details
