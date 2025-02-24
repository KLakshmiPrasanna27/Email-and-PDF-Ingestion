"Email & PDF Ingestion with Simple UI" project. This will include:

Frontend (Next.js + TypeScript)

Backend API (Next.js API routes)

Database (PostgreSQL + Prisma)

Email Ingestion (IMAP for fetching emails)

PDF Processing (Extracting text from PDFs)
PDF Processing: Extract text from PDF attachments

Deployment: Vercel
Setup and Installation

Step 1: Clone the Repository

git clone https://github.com/your-username/email-pdf-ingestion.git
cd email-pdf-ingestion

Step 2: Install Dependencies

npm install

Step 3: Set Up Environment Variables

Create a .env file in the project root and add the following:

DATABASE_URL=postgresql://user:password@localhost:5432/emailpdfdb
IMAP_HOST=imap.gmail.com
IMAP_USER=your-email@gmail.com
IMAP_PASSWORD=your-email-password

Step 4: Set Up PostgreSQL Database

Ensure PostgreSQL is running, then initialize Prisma:

npx prisma migrate dev --name init

Step 5: Run the Development Server

npm run dev


---

Project Structure

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

1. Email Configuration API

GET /api/email-config

Fetch all email configurations.

curl -X GET http://localhost:3000/api/email-config

POST /api/email-config

Save a new email configuration.

curl -X POST http://localhost:3000/api/email-config \
  -H "Content-Type: application/json" \
  -d '{"email": "test@example.com"}'

2. Email Fetching API (IMAP)

Fetch emails from the configured email account.

curl -X GET http://localhost:3000/api/email

Contributors

KASARLA LAKSHMI PRASANNA
License

This project is licensed under the MIT License.
