# Jai Vidarbha API Specification

## Base URL
```
https://api.jaividarbha.com/v1
```

## Authentication
All endpoints (except `/auth/register` and `/auth/login`) require JWT token in Authorization header:
```
Authorization: Bearer {token}
```

## Response Format
```json
{
  "success": true,
  "data": {...},
  "message": "Operation successful",
  "timestamp": "2024-01-15T10:30:00Z"
}
```

## Auth Service

### Register User
```
POST /auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "phone": "+919876543210",
  "password": "SecurePassword123!",
  "firstName": "John",
  "lastName": "Doe",
  "title": "Mr",
  "language": "en"
}
```

### Login
```
POST /auth/login
Content-Type: application/json

{
  "emailOrPhone": "user@example.com",
  "password": "SecurePassword123!"
}
```

### Verify OTP
```
POST /auth/verify-otp
Content-Type: application/json

{
  "emailOrPhone": "user@example.com",
  "otp": "123456"
}
```

## User Profile Service

### Get User Profile
```
GET /profile/{userId}
Authorization: Bearer {token}
```

### Update User Profile
```
PUT /profile/{userId}
Authorization: Bearer {token}
Content-Type: application/json

{
  "firstName": "John",
  "lastName": "Doe",
  "dateOfBirth": "1990-05-15",
  "district": "Nagpur",
  "profession": "Business Owner"
}
```

## Member Management Service

### Add New Member
```
POST /members
Authorization: Bearer {token}
Content-Type: application/json

{
  "firstName": "Jane",
  "lastName": "Smith",
  "phone": "+919876543210",
  "district": "Nagpur",
  "referrerUserId": "uuid-xxx",
  "referralMessage": "Interested in joining party"
}
```

### Get Members
```
GET /members?district=Nagpur&status=ACTIVE&limit=20&offset=0
Authorization: Bearer {token}
```

### Get Referral History
```
GET /members/referral/{userId}
Authorization: Bearer {token}
```

## Donation Service

### Create Donation
```
POST /donations
Authorization: Bearer {token}
Content-Type: application/json

{
  "amount": 5000,
  "currency": "INR",
  "description": "Party funding contribution"
}
```

### Get Donation History
```
GET /donations/history/{userId}?limit=20&offset=0
Authorization: Bearer {token}
```

## Issue Management Service

### Report Issue
```
POST /issues
Authorization: Bearer {token}
Content-Type: application/json

{
  "category": "PARTY_INSIDE_ISSUES",
  "title": "Issue Title",
  "description": "Detailed description",
  "level": "TALUKA"
}
```

### Get Issues
```
GET /issues?category=PARTY_INSIDE_ISSUES&status=OPEN&limit=20
Authorization: Bearer {token}
```

## Event Management Service

### Create Event
```
POST /events
Authorization: Bearer {token}
Content-Type: application/json

{
  "title": "Party Meeting",
  "description": "Monthly meeting",
  "eventType": "MEETING_ROSTER",
  "startDate": "2024-02-01",
  "location": "Nagpur, Maharashtra"
}
```

### Get Monthly Calendar
```
GET /events/calendar/2024-01
Authorization: Bearer {token}
```

## Social Media Service

### Link Social Media Account
```
POST /social/link-account
Authorization: Bearer {token}
Content-Type: application/json

{
  "platform": "FACEBOOK",
  "accountId": "facebook_account_id",
  "accessToken": "facebook_access_token"
}
```

### Get Social Media News Feed
```
GET /social/news-feed?limit=20&offset=0
Authorization: Bearer {token}
```

## Communication Service

### Send Notification
```
POST /communication/send
Authorization: Bearer {token}
Content-Type: application/json

{
  "userId": "uuid-xxx",
  "type": "EVENT_NOTIFICATION",
  "title": "New Event",
  "message": "A new event has been scheduled"
}
```
