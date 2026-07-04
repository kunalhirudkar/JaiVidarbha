# Jai Vidarbha - System Architecture

## Overview

Jai Vidarbha is a microservices-based platform designed to manage political party operations, member engagement, donations, and community outreach through a Flutter mobile application.

## Microservices

### 1. Authentication Service
**Purpose**: User authentication, registration, and authorization
- User registration with email/phone
- OTP-based verification (SMS gateway integration)
- Password reset functionality
- JWT token management
- Multi-role support

### 2. User Profile Service
**Purpose**: Manage user profile information and preferences
- Personal profile data (name, contact, interests)
- Profession and background tracking
- Location management (current & permanent)
- Language and preference settings
- Profile photo management

### 3. Member Management Service
**Purpose**: Manage party member hierarchy and relationships
- Add and manage party members
- Hierarchical levels: Village → Taluka → District → Division
- Party roles: President, Vice President, Speaker, Chairperson, etc.
- Referral tracking with status
- Member-to-member relationships

### 4. Donation Service
**Purpose**: Handle donations and payment processing
- Multiple payment methods: RuPay, Credit Card, Debit Card, UPI/BHIM
- Donation creation and tracking
- Payment processing and status management
- Donation history and reporting
- Banking partner integration

### 5. Issue Management Service
**Purpose**: Manage party-related issues and problem reporting
- Issue categories: Party Inside, Party Outside, Women-specific
- Subcategories: Member problems, promotion kits, meeting conflicts, etc.
- Issue tracking and status updates
- Comment threads with attachments
- Level-based issue assignment

### 6. Event Management Service
**Purpose**: Manage party events, calendars, and event posters
- Event creation and scheduling
- Event types: Birthdays, Anniversaries, Protests, Meetings, etc.
- Monthly calendar view
- Event poster creation and sharing
- Attendance tracking

### 7. Social Media Service
**Purpose**: Manage social media integrations and content
- Link social media accounts (Facebook, Twitter, Instagram)
- Create and schedule posts
- Event poster creation for social sharing
- Party news feed aggregation
- Content analytics

### 8. Communication Service
**Purpose**: Handle notifications and level-based communications
- OTP delivery via SMS
- Event notifications
- Issue status updates
- Member notifications
- Admin broadcasts
- Level-specific communications (e.g., to Taluka heads only)

### 9. Content Management Service
**Purpose**: Manage platform content, languages, and policies
- Multi-language support (English, Marathi, Hindi)
- Privacy policy and terms management
- File upload and storage
- Content translations
- Platform configuration

## Data Layer

### PostgreSQL Database
- Core data storage
- ACID compliance
- Read replicas for scaling
- Automated backups

### Redis Cache
- Session management
- OTP storage (temporary)
- Frequently accessed data
- Rate limiting

### Message Queue (RabbitMQ)
- Asynchronous task processing
- Email/SMS sending
- Notification delivery
- Event-driven architecture

## External Integrations

- **SMS Gateway**: Twilio/AWS SNS for OTP and notifications
- **Payment Gateway**: RuPay API for donation processing
- **Email Service**: SendGrid for email communications
- **Social Media APIs**: Facebook, Twitter, Instagram
- **Cloud Storage**: AWS S3 for file storage
- **Firebase** (Optional): Real-time communication and push notifications
