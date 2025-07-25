# Expense Tracker - Full Stack Application

A modern, responsive expense tracking application built with React, Express, TypeScript, and PostgreSQL. Track your income and expenses with real-time balance calculations and beautiful UI.

## 🚀 Features

- **Transaction Management**: Add, view, and delete income/expense transactions
- **Real-time Calculations**: Automatic balance updates and financial summaries
- **Modern UI**: Built with shadcn/ui components and Tailwind CSS
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Database Persistence**: PostgreSQL database with Drizzle ORM
- **Indian Rupees Support**: Currency formatting in INR
- **Category System**: Organize transactions by categories
- **Transaction Filtering**: Filter by income, expense, or view all transactions

## 🛠️ Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development and optimized builds
- **Tailwind CSS** with shadcn/ui component library
- **TanStack Query** for server state management
- **React Hook Form** with Zod validation
- **Wouter** for lightweight client-side routing

### Backend
- **Node.js** with Express.js framework
- **TypeScript** with ES modules
- **PostgreSQL** with Neon serverless driver
- **Drizzle ORM** for type-safe database operations
- **Zod** for request/response validation

### Database
- **PostgreSQL** with persistent storage
- **Drizzle Kit** for schema management
- **Shared TypeScript schemas** between client and server

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd expense-tracker
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file with your database URL:
   ```env
   DATABASE_URL=your_postgresql_connection_string
   ```

4. **Database Setup**
   ```bash
   npm run db:push
   ```

5. **Start the application**
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:5000`

## 🏗️ Project Structure

```
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Application pages
│   │   ├── hooks/          # Custom React hooks
│   │   └── lib/            # Utility functions and configs
├── server/                 # Backend Express application
│   ├── db.ts              # Database connection
│   ├── storage.ts         # Data access layer
│   ├── routes.ts          # API routes
│   └── index.ts           # Server entry point
├── shared/                 # Shared TypeScript schemas
│   └── schema.ts          # Database and validation schemas
└── package.json           # Dependencies and scripts
```

## 🔗 API Endpoints

- `GET /api/transactions` - Retrieve all transactions (supports ?type=income|expense filter)
- `POST /api/transactions` - Create new transaction
- `DELETE /api/transactions/:id` - Delete transaction
- `GET /api/summary` - Get financial summary (total income, expenses, balance)

## 🎨 UI Components

The application uses a comprehensive set of UI components:
- Form components with validation
- Cards and layouts
- Buttons with multiple variants
- Input fields with icons
- Select dropdowns
- Toast notifications
- Responsive design patterns

## 💾 Database Schema

### Transactions Table
- `id`: UUID primary key
- `type`: Enum ('income' or 'expense')
- `amount`: Decimal amount in INR
- `description`: Text description
- `category`: Optional category field
- `createdAt`: Timestamp

## 🚀 Deployment

The application is designed for easy deployment on platforms supporting Node.js:

1. **Build the application**
   ```bash
   npm run build
   ```

2. **Set environment variables**
   - `DATABASE_URL`: PostgreSQL connection string
   - `NODE_ENV`: Set to 'production'

3. **Deploy to your preferred platform**
   - Vercel, Netlify, Railway, Render, etc.
   - Ensure PostgreSQL database is accessible

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 👤 Author

**Your Name**
Name - Sumit Kumar
- LinkedIn: [https://www.linkedin.com/in/krsumit78/]
- GitHub: [https://github.com/krsumit7]

---

