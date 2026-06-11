# Lead Management System

A professional, full-stack lead management system for tracking and managing sales leads with real-time updates, analytics, and activity logging.

## Features

- **Lead Management**
  - Create, read, update, and delete leads
  - Track lead details (name, email, phone, company, position)
  - Assign leads to team members
  - Add custom notes to leads

- **Status Tracking**
  - New, Contacted, Qualified, Negotiating, Closed
  - Filter leads by status
  - Quick status updates

- **Lead Analytics**
  - Dashboard with key metrics
  - Total leads count
  - New leads count
  - Qualified leads count
  - Total pipeline value

- **Activity Logging**
  - Automatic activity tracking for lead creation and status changes
  - Manual activity logging
  - Complete activity history per lead

- **Lead Sources**
  - Website, Referral, Social Media
  - Email Campaign, Phone Call, Event
  - Categorize leads by source

- **Responsive Design**
  - Works on desktop, tablet, and mobile
  - Clean, modern UI
  - Real-time updates

## Tech Stack

**Backend:**
- Node.js with Express.js
- SQLite database
- RESTful API

**Frontend:**
- HTML5
- CSS3 with responsive design
- Vanilla JavaScript (no dependencies)

## Installation

### Prerequisites
- Node.js (v14 or higher)
- npm

### Setup Steps

1. **Navigate to project directory:**
   ```bash
   cd "LEAD MANAGEMENT SYSTEM"
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the server:**
   ```bash
   npm start
   ```

4. **Open in browser:**
   ```
   http://localhost:3000
   ```

## Project Structure

```
LEAD MANAGEMENT SYSTEM/
├── .github/
│   └── copilot-instructions.md
├── src/
│   ├── server.js              # Express server entry point
│   ├── database.js            # SQLite database setup
│   └── routes/
│       └── leads.js           # Lead API endpoints
├── public/
│   ├── index.html             # Main HTML file
│   ├── styles.css             # Styling
│   └── app.js                 # Frontend JavaScript
├── database/                  # SQLite database directory
├── .env                       # Environment variables
├── .gitignore
├── package.json
└── README.md
```

## API Endpoints

### Leads

**GET** `/api/leads`
- Get all leads
- Response: Array of lead objects

**GET** `/api/leads/:id`
- Get single lead with activities
- Response: Lead object with activities array

**POST** `/api/leads`
- Create new lead
- Body: `{ firstName, lastName, email, phone, company, position, source, leadValue, notes, assignedTo }`
- Response: `{ id, message }`

**PUT** `/api/leads/:id`
- Update lead
- Body: Lead object with fields to update
- Response: `{ message }`

**DELETE** `/api/leads/:id`
- Delete lead
- Response: `{ message }`

**POST** `/api/leads/:id/activities`
- Add activity to lead
- Body: `{ activityType, description }`
- Response: `{ message }`

## Database Schema

### leads table
```sql
CREATE TABLE leads (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  firstName TEXT NOT NULL,
  lastName TEXT NOT NULL,
  email TEXT,
  phone TEXT,
  company TEXT,
  position TEXT,
  status TEXT DEFAULT 'New',
  source TEXT,
  leadValue REAL,
  notes TEXT,
  createdAt DATETIME DEFAULT CURRENT_TIMESTAMP,
  updatedAt DATETIME DEFAULT CURRENT_TIMESTAMP,
  assignedTo TEXT
)
```

### activities table
```sql
CREATE TABLE activities (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  leadId INTEGER NOT NULL,
  activityType TEXT,
  description TEXT,
  createdAt DATETIME DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (leadId) REFERENCES leads(id) ON DELETE CASCADE
)
```

## Usage Guide

### Adding a Lead
1. Click "Add New Lead" button
2. Fill in the form with lead information
3. Select appropriate status, source, and assign to team member
4. Click "Save Lead"

### Editing a Lead
1. Click "Edit" button on the lead row or in detail view
2. Update the information
3. Click "Save Lead"

### Viewing Lead Details
1. Click on lead name in the table
2. View complete lead information and activity history
3. Edit or delete from this view

### Filtering Leads
1. Use the "Status" dropdown filter
2. Select a status to view only leads with that status
3. Select "All Statuses" to see all leads

### Tracking Activities
- Activities are automatically logged for:
  - New lead creation
  - Status changes
  - Manual activity entries
- All activities are timestamped and visible in lead details

## Environment Variables

Create a `.env` file in the root directory:

```
PORT=3000
NODE_ENV=development
DB_PATH=./database/leads.db
```

## Development

### Starting in Development Mode
```bash
npm run dev
```

### Database Reset
To start fresh with an empty database:
1. Delete `database/leads.db`
2. Restart the server
3. Tables will be recreated automatically

## Troubleshooting

### Port Already in Use
If port 3000 is already in use, change it in `.env`:
```
PORT=3001
```

### Database Errors
- Ensure `/database` directory exists
- Check file permissions
- Delete `leads.db` to reset database

### Frontend Not Loading
- Verify server is running (`npm start`)
- Check browser console for errors
- Ensure public files are in correct location

## Features Coming Soon

- User authentication and roles
- Advanced analytics and reporting
- Email notifications
- Integration with email/calendar
- Bulk import/export
- Custom fields
- Pipeline views
- Scheduled follow-ups

## License

ISC

## Support

For issues or questions, please check the troubleshooting section or contact your administrator.
