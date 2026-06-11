# 🚀 Deploy Your Lead Management System Online

Your Lead Management System is ready to deploy! Here's how to get it live on the internet for **FREE**.

## Option 1: Deploy to Vercel (EASIEST - Recommended) ⭐

Vercel is the easiest way to deploy Node.js applications. Your site will be live in minutes!

### Step 1: Push Code to GitHub

1. **Create a GitHub account** (if you don't have one): https://github.com/signup
2. **Create a new repository**:
   - Go to https://github.com/new
   - Name it: `lead-management-system`
   - Click "Create repository"

3. **Push your code to GitHub**:
   Open PowerShell in your project folder and run:
   ```powershell
   git init
   git add .
   git commit -m "Initial commit: Lead Management System"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/lead-management-system.git
   git push -u origin main
   ```
   (Replace `YOUR_USERNAME` with your GitHub username)

### Step 2: Deploy to Vercel

1. **Go to Vercel**: https://vercel.com/signup
2. **Sign up with GitHub** (choose this option)
3. **Select your repository**: `lead-management-system`
4. **Click "Deploy"**
5. **Wait 1-2 minutes** and your site is LIVE! 🎉

Your site will get a URL like: `https://lead-management-system-xyz.vercel.app`

---

## Option 2: Deploy to Render (Good Alternative)

### Step 1-2: Same as Vercel (push to GitHub)

### Step 3: Deploy to Render

1. **Go to Render**: https://render.com
2. **Click "New +"** → **"Web Service"**
3. **Connect GitHub** and select your repository
4. **Settings**:
   - Name: `lead-management-system`
   - Environment: `Node`
   - Build Command: `npm install`
   - Start Command: `npm start`
5. **Click "Create Web Service"**
6. **Wait 5 minutes** for deployment to complete

Your site will get a URL like: `https://lead-management-system.onrender.com`

---

## Option 3: Deploy to Replit (Easiest - No GitHub needed)

1. **Go to Replit**: https://replit.com/signup
2. **Click "Import from GitHub"** or upload files directly
3. **Select Node.js** as the language
4. **Click "Run"**
5. Your app starts immediately!
6. **Share your link** from the "Webview" tab

---

## Local Testing First (Recommended)

Before deploying online, test locally:

1. **Install Node.js**: https://nodejs.org/ (LTS version)
2. **In your project folder**:
   ```powershell
   npm install
   npm start
   ```
3. **Visit**: http://localhost:3000

---

## Important: Database Note

The system uses SQLite for the database. 

- **Local**: Works perfectly! Database file saves in `/database/leads.db`
- **Vercel/Online**: ⚠️ SQLite doesn't persist on Vercel free tier

### For Production (Optional Upgrade):

If you want to keep data when redeploying, you can:
1. **Upgrade database** to MongoDB (free tier available)
2. **Use Vercel's paid tier** (supports persistent storage)
3. **Use a different host** like Render with persistent storage

For now, the free tier works great for testing and development!

---

## Testing Your Deployed Site

Once deployed, test these features:

1. ✅ Visit your URL
2. ✅ Add a test lead
3. ✅ View the dashboard
4. ✅ Filter leads by status
5. ✅ Edit and delete leads
6. ✅ Check the API: `https://your-domain.com/api/health`

---

## Your Domain Name

Free domains available:
- **.vercel.app** - Automatic with Vercel
- **.onrender.com** - Automatic with Render
- **.replit.dev** - Automatic with Replit

Want a custom domain? Add it for $12/year:
- **namecheap.com** - Budget domains
- **godaddy.com** - Popular registrar

---

## Environment Variables for Production

On your hosting platform, set these environment variables:

```
PORT=3000
NODE_ENV=production
DB_PATH=/tmp/leads.db
```

---

## Next Steps After Deployment

### If Data Persists:
✅ Your system is ready to use!

### If You Want Persistent Data:
1. **Upgrade to paid hosting**, OR
2. **Switch to a cloud database** (MongoDB, PostgreSQL)

---

## Troubleshooting Deployment

**Q: "Build failed" error**
- Check that all files were pushed to GitHub
- Verify package.json exists in root folder

**Q: "Cannot connect to database"**
- Normal for free tier - data won't persist on redeploy
- For production, upgrade to paid tier or use cloud database

**Q: "Port already in use"**
- Hosting platform handles this automatically

---

## Quick Deploy Commands

### For Vercel CLI (if installed):
```powershell
npm install -g vercel
vercel
```

### For Git/GitHub:
```powershell
git add .
git commit -m "Updates"
git push
```

---

## Questions?

- **GitHub Help**: https://docs.github.com/en/get-started
- **Vercel Docs**: https://vercel.com/docs
- **Node.js Docs**: https://nodejs.org/docs/

---

**Choose your hosting above and your Lead Management System will be live in minutes!** 🚀
