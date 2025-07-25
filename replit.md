# Expense Tracker - Full Stack Application

## Overview

This is a full-stack expense tracking application built with React, Express, TypeScript, and PostgreSQL. The application allows users to track their income and expenses with a modern, responsive interface built using shadcn/ui components.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state management
- **Form Handling**: React Hook Form with Zod validation
- **Routing**: Wouter for lightweight client-side routing
- **UI Components**: Radix UI primitives with custom styling

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Style**: RESTful API with JSON responses
- **Validation**: Zod schemas for request/response validation
- **Development**: tsx for TypeScript execution in development

### Data Storage Solutions
- **Database**: PostgreSQL with Neon serverless driver
- **ORM**: Drizzle ORM for type-safe database operations
- **Migrations**: Drizzle Kit for schema management
- **Schema**: Shared TypeScript schema definitions between client and server

### Authentication and Authorization
- **Current State**: No authentication implemented 
- **Session Management**: Express sessions with PostgreSQL store (configured but not actively used)

## Key Components

### Database Schema
- **Transactions Table**: Stores income and expense records with fields:
  - `id`: UUID primary key
  - `type`: Enum ('income' or 'expense')
  - `amount`: Decimal amount
  - `description`: Text description
  - `category`: Optional category field
  - `createdAt`: Timestamp

### API Endpoints
- `GET /api/transactions` - Retrieve all transactions or filter by type
- `POST /api/transactions` - Create new transaction
- `DELETE /api/transactions/:id` - Remove transaction

### Frontend Features
- Transaction form with type selection (income/expense)
- Real-time balance calculation
- Transaction filtering and listing
- Responsive design with mobile support
- Toast notifications for user feedback

### Storage Layer
- **Current**: PostgreSQL database with Drizzle ORM for persistent storage
- **Previous**: In-memory storage (migrated to PostgreSQL on January 25, 2025)
- **Interface**: Abstract storage interface allowing easy switching between implementations

## Data Flow

1. **User Input**: Forms collect transaction data with client-side validation
2. **Validation**: Zod schemas validate data on both client and server
3. **API Communication**: TanStack Query manages HTTP requests and caching
4. **Server Processing**: Express routes handle business logic and data persistence
5. **Database Operations**: Drizzle ORM provides type-safe database queries
6. **State Updates**: React Query automatically updates UI when data changes

## External Dependencies

### Core Dependencies
- **Database**: @neondatabase/serverless for PostgreSQL connectivity
- **ORM**: drizzle-orm and drizzle-zod for database operations
- **Validation**: zod for schema validation
- **UI Framework**: Multiple @radix-ui components for accessible UI primitives
- **Styling**: tailwindcss, class-variance-authority, clsx for styling
- **Forms**: react-hook-form with @hookform/resolvers for form management
- **HTTP Client**: TanStack Query for API state management

### Development Tools
- **Build**: Vite with React plugin
- **TypeScript**: Full TypeScript support with strict configuration
- **Linting**: ESLint and Prettier (implied by file structure)
- **Database Tools**: Drizzle Kit for migrations and schema management

## Deployment Strategy

### Build Process
- **Client**: Vite builds React app to `dist/public`
- **Server**: esbuild bundles Node.js server to `dist/index.js`
- **Assets**: Static files served from built client directory

### Environment Configuration
- **Database**: Requires `DATABASE_URL` environment variable
- **Development**: Uses tsx for TypeScript execution
- **Production**: Runs compiled JavaScript with Node.js

### Hosting Considerations
- Designed for deployment on platforms supporting Node.js
- PostgreSQL database required (Neon recommended for serverless)
- Static assets can be served from CDN if needed
- Environment variables needed for database connection

### Development vs Production
- **Development**: PostgreSQL storage, hot reloading, source maps
- **Production**: PostgreSQL storage, optimized builds, error handling
- **Database**: Drizzle handles schema synchronization across environments

## Recent Changes
- **January 25, 2025**: 
  - Changed currency from USD to Indian Rupees (INR)
  - Migrated from in-memory storage to PostgreSQL database
  - Updated storage layer to use DatabaseStorage with Drizzle ORM