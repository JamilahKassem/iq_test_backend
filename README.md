# Project Title

A simple full‑stack application with a Node.js backend (Express, WebSocket, MySQL) and a Next.js frontend.

## Tech stack

- **Backend**: Node.js, Express, ws (WebSockets), mysql2  
- **Frontend**: Next.js (React)  
- **Runtime**: Node.js (LTS recommended)

## Prerequisites

Before you start, make sure you have:

- Node.js installed (LTS version recommended).  
- npm installed (it comes with Node.js).

You can verify the installation with:

```markdown
node -v
npm -v
```

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install backend dependencies

From the project root (where `server.js` and `package.json` live for the backend), run:

```bash
npm install
```

> Note: The command should be `npm install`, not `node install`. `npm install` reads `package.json` and installs all required packages into `node_modules`.

This will install:

- express  
- ws  
- mysql2  
- any other dependencies listed in `package.json`

## Configuration

Depending on your setup, you may need environment variables for:

- MySQL connection (host, port, user, password, database name)  
- Backend server port  
- WebSocket URL used by the frontend

## Database setup

The project requires a database that the backend will connect to. The SQL file needed to create and seed this database is included in the project files.

1. Locate the SQL file in the project (for example `schema.sql`, `database.sql`, or similar).
2. Import or run this SQL file in your database server (e.g., MySQL or MariaDB) using your preferred tool:
   - A GUI client (like MySQL Workbench, phpMyAdmin, etc.), or
   - Command line:

     ```bash
     mysql -u YOUR_USER -p YOUR_DATABASE < path/to/file.sql
     ```

3. Ensure the backend’s database configuration matches the database name, user, and password you used when creating the database.
4. Make sure the database is configured correctly for the server in the env file.

> Note: The actual database connection is handled by the backend; the frontend just assumes the backend and database are configured and running.

## Running the backend server

From the directory that contains `server.js`:

```bash
node server.js
```

- This starts the Express server.  
- The same process also initializes WebSocket support via `ws`.  
- The server will connect to MySQL using `mysql2` with the configuration defined in your code (and `.env` if used).

Keep this terminal window open while you run the frontend.


## Project structure (example)

Adjust this to match your actual folders:

```text
.
─ backend/          # Next.js app
│  ├─ server.js    # Frontend dependencies
│  └─ ...
└─ README.md
├─ frontend/          # Next.js app
│  ├─ package.json    # Frontend dependencies
│  └─ ...
└─ README.md
```

## Typical workflow

1. Start the database server (with the schema loaded from the provided SQL file).
2. Start the backend server (listening on ports 9001 and 9002 for WebSockets).
3. Start the frontend:

   ```bash
   npm run dev
   ```

4. Open `http://localhost:3000` in your browser and interact with the app.

## Common issues

- If `node server.js` fails, check:
  - That `npm install` was run in the backend folder.
  - That MySQL is running and credentials are correct.
- If the frontend cannot reach the backend:
  - Verify the backend port and URL used in the Next.js code.
  - Confirm the backend terminal shows “listening on port …” (or similar log).
- **Database-related issues**
  - Ensure the SQL file was imported correctly into your database.
  - Confirm that the backend configuration (database name, user, password, host) matches your database setup.
