# SETUP GUIDE - Lead Management System

## ✅ What's Been Created

Your Lead Management System is now scaffolded with all the necessary files:

```
LEAD MANAGEMENT SYSTEM/
├── .github/
│   └── copilot-instructions.md
├── .vscode/
│   └── tasks.json
├── src/
│   ├── server.js
│   ├── database.js
│   └── routes/
│       └── leads.js
├── public/
│   ├── index.html
│   ├── styles.css
│   └── app.js
├── database/           (empty - will be created on first run)
├── .env
├── .gitignore
├── package.json
└── README.md
```

## 🚀 Next Steps to Get Running

### Step 1: Install Node.js
You need to install Node.js first. Download and install from: https://nodejs.org/

**Choose the LTS (Long Term Support) version** - it's the most stable for production use.

### Step 2: Install Dependencies
After Node.js is installed, open PowerShell/Terminal in this directory and run:

```powershell
npm install
```

This will install:
- Express.js (web server framework)
- SQLite3 (database)
- Body-parser (request parsing)
- CORS (cross-origin requests)
- Dotenv (environment variables)

### Step 3: Start the Server
Run:

```powershell
npm start
```

You should see:
```
Lead Management System server running on port 3000
Visit http://localhost:3000 in your browser
```

### Step 4: Open in Browser
Visit: **http://localhost:3000**

You'll see the Lead Management System dashboard!

## 💡 Features You Can Start Using Immediately

✅ **Add Leads** - Create new sales leads with full details
✅ **Track Status** - Manage lead pipeline (New → Contacted → Qualified → Negotiating → Closed)
✅ **Dashboard** - See key metrics (total leads, new leads, qualified leads, pipeline value)
✅ **Filter** - Filter leads by status
✅ **Edit & Delete** - Update or remove leads
✅ **Activity Log** - Track all interactions with each lead
✅ **Responsive UI** - Works on desktop, tablet, and mobile
✅ **Assign Leads** - Assign leads to team members

## 🛠️ API Endpoints (Backend)

The system provides a complete REST API:

```
GET    /api/leads              - Get all leads
GET    /api/leads/:id          - Get single lead with activities
POST   /api/leads              - Create new lead
PUT    /api/leads/:id          - Update lead
DELETE /api/leads/:id          - Delete lead
POST   /api/leads/:id/activities - Add activity to lead
```

## 📊 Database

SQLite database is automatically created on first run:
- Location: `/database/leads.db`
- Tables: `leads` and `activities`
- No setup needed!

## ⚡ VS Code Integration

If using VS Code, you can use the built-in Tasks:
1. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
2. Type "Tasks: Run Task"
3. Select "Start Lead Management System"

## 🔧 Development Tips

### Change Port
Edit `.env`:
```
PORT=3001
```

### Reset Database
Delete `database/leads.db` file and restart server - it will recreate tables.

### Check Server Health
Visit: http://localhost:3000/api/health

## 📝 Environment Variables

The `.env` file controls:
```
PORT=3000                    # Server port
NODE_ENV=development         # Environment mode
DB_PATH=./database/leads.db # Database location
```

## 🚨 Troubleshooting

**Q: "npm: The term 'npm' is not recognized"**
A: You need to install Node.js first from https://nodejs.org/

**Q: "Port 3000 already in use"**
A: Change PORT in `.env` file to 3001 or another available port

**Q: "Database errors"**
A: Delete `database/leads.db` file and restart - it will auto-create

**Q: "Cannot GET /"**
A: Make sure server is running with `npm start`

## 📚 For More Information

- See [README.md](README.md) for complete documentation
- Check [package.json](package.json) for dependencies
- Review `.github/copilot-instructions.md` for project notes

## ✨ What's Next?

Once everything is running, you can:
1. Add some test leads
2. Try filtering by status
3. Check the activity log
4. Explore the API with tools like Postman or Insomnia

---

**Questions?** Check the README.md or restart VS Code's Copilot chat for assistance!

Happy lead managing! 🎉
