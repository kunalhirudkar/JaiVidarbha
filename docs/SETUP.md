# Jai Vidarbha - Development Setup Guide

## Prerequisites

- Git
- Docker & Docker Compose
- Node.js 18+
- Flutter 3.10+
- PostgreSQL 13+ client tools

## Quick Start

### 1. Clone Repository

```bash
git clone https://github.com/kunalhirudkar/JaiVidarbha.git
cd JaiVidarbha
```

### 2. Start Infrastructure

```bash
docker-compose up -d
```

This will start:
- PostgreSQL (port 5432)
- Redis (port 6379)
- RabbitMQ (port 5672, admin: 15672)

### 3. Environment Setup

Create `.env` file:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=jai_vidarbha
DB_USER=postgres
DB_PASSWORD=postgres_password_123

REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=redis_password_123

JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRY=24h

API_GATEWAY_PORT=3000
SMS_GATEWAY_API_KEY=your_sms_api_key
RUPAY_API_KEY=your_rupay_api_key

ENVIRONMENT=development
```

### 4. Backend Services Setup

```bash
# Create service directories
mkdir -p backend/{auth-service,user-profile-service,member-management-service,donation-service,issue-management-service,event-management-service,social-media-service,communication-service,content-management-service,api-gateway}

# Install dependencies for each service
for service in backend/*/; do
  cd "$service"
  npm install
  cd ../../
done
```

### 5. Start Services

```bash
# Terminal 1 - API Gateway
cd backend/api-gateway
npm start

# Terminal 2 - Auth Service
cd backend/auth-service
npm start

# Terminal 3 - User Profile Service
cd backend/user-profile-service
npm start

# And so on for other services...
```

### 6. Flutter App Setup

```bash
cd flutter_app

# Get dependencies
flutter pub get

# Run on emulator/device
flutter run
```

## Verification

```bash
# Check API Gateway
curl http://localhost:3000/health

# Check PostgreSQL
psql -h localhost -U postgres -d jai_vidarbha

# Check Redis
redis-cli -h localhost ping
```

## Database Migration

Database migrations will be implemented in the respective services.

## API Documentation

See [API_SPECIFICATION.md](API_SPECIFICATION.md) for detailed API documentation.

## Troubleshooting

### Port Already in Use
```bash
lsof -ti:3000 | xargs kill -9
```

### Database Connection Failed
```bash
docker-compose restart postgres
```

### Redis Connection Issues
```bash
docker-compose restart redis
```
