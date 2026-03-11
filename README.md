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

## Common issues

- If `node server.js` fails, check:
  - That `npm install` was run in the backend folder.
  - That MySQL is running and credentials are correct.
- If the frontend cannot reach the backend:
  - Verify the backend port and URL used in the Next.js code.
  - Confirm the backend terminal shows “listening on port …” (or similar log).
```
