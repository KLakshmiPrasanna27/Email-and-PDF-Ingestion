Email & PDF Ingestion with Simple UI

Overview

This project is designed to facilitate the ingestion of emails and extraction of PDF attachments using a full-stack approach. The system is built using Next.js with TypeScript for the frontend, Next.js API routes for backend logic, PostgreSQL with Prisma ORM for data storage, and IMAP for fetching emails. Additionally, PDF parsing is implemented to extract and store relevant information from email attachments.

Setup and Installation

To begin using this project, follow the step-by-step instructions below:

Step 1: Clone the Repository

To get started, clone the repository from GitHub and navigate to the project directory using the following commands:

git clone https://github.com/your-username/email-pdf-ingestion.git
cd email-pdf-ingestion

Step 2: Install Dependencies

Ensure you have Node.js installed, then run the following command to install all necessary dependencies:

npm install

Step 3: Set Up Environment Variables

Before running the application, create a .env file in the root directory and configure it with the required database and email settings:

DATABASE_URL=postgresql://user:password@localhost:5432/emailpdfdb
IMAP_HOST=imap.gmail.com
IMAP_USER=your-email@gmail.com
IMAP_PASSWORD=your-email-password

Step 4: Set Up PostgreSQL Database

Ensure that PostgreSQL is installed and running on your machine. Then, initialize the database schema using Prisma:

npx prisma migrate dev --name init

This will create the necessary database tables and apply migrations.

Step 5: Run the Development Server

Once everything is set up, start the development server with:

npm run dev

This will launch the application on http://localhost:3000/.

Project Structure

This project follows a structured directory layout to maintain modularity and organization:

email-pdf-ingestion/
│── prisma/                # Prisma schema and migrations
│── app/
│   ├── api/
│   │   ├── email-config/  # API routes for email config
│── utils/
│   ├── emailFetcher.ts    # IMAP email fetching logic
│   ├── pdfProcessor.ts    # PDF parsing logic
│── .env                   # Environment variables
│── package.json           # Project dependencies
│── README.md              # Documentation

API Endpoints

The system provides the following API endpoints:

1. Email Configuration API

GET /api/email-config

Fetches all stored email configurations.

curl -X GET http://localhost:3000/api/email-config

POST /api/email-config

Stores a new email configuration in the database.

curl -X POST http://localhost:3000/api/email-config \
  -H "Content-Type: application/json" \
  -d '{"email": "test@example.com"}'

2. Email Fetching API (IMAP)

Retrieves emails from the configured email account.

curl -X GET http://localhost:3000/api/emails

Deployment

Once development is complete, the project can be deployed to Vercel for hosting. Follow these steps:

Step 1: Deploy to Vercel

Install Vercel CLI globally, log in, and deploy the project:

npm install -g vercel
vercel login
vercel

Follow the instructions provided by Vercel to complete the deployment.

Step 2: Push to GitHub

Version control is managed using GitHub. Push the project to a repository using the following commands:

git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/your-username/email-pdf-ingestion.git
git push -u origin main

Contributors

This project is maintained by:

KASARLA LAKSHMI PRASANNA


License

This project is licensed under the MIT License, allowing open-source usage and modification.
