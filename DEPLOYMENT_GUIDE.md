# 🚀 Frontend Deployment Guide - Step by Step

## 📋 Prerequisites

✅ You have a GitHub account  
✅ You have a Vercel account (free tier is fine)  
✅ Your backend API is deployed at: `https://fcrules.vercel.app`  

## 🎯 Deployment Steps

### Step 1: Create a New GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `fcrules-frontend` (or any name you like)
3. Description: "Football Laws of the Game - AI-powered frontend"
4. Keep it **Public** or **Private** (your choice)
5. **DO NOT** initialize with README (we already have files)
6. Click "Create repository"

### Step 2: Push Your Code to GitHub

```bash
# Navigate to the frontend folder
cd frontend

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: Football Law frontend"

# Add your GitHub repository as remote
# Replace YOUR_USERNAME with your GitHub username
git remote add origin https://github.com/YOUR_USERNAME/fcrules-frontend.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Deploy to Vercel

#### Option A: Via Vercel Dashboard (Easier)

1. **Go to Vercel**: [vercel.com/new](https://vercel.com/new)

2. **Import Git Repository**
   - Click "Import Git Repository"
   - Select your `fcrules-frontend` repository
   - Click "Import"

3. **Configure Project**
   - Project Name: `fcrules-frontend` (or leave as auto-generated)
   - Framework Preset: **Other** (or leave as detected)
   - Root Directory: `./` (leave as default)
   - Build Settings: Leave everything as default
   - **No environment variables needed for frontend!**

4. **Deploy**
   - Click "Deploy"
   - Wait 30-60 seconds
   - 🎉 Your frontend is live!

#### Option B: Via Vercel CLI

```bash
# Install Vercel CLI globally
npm install -g vercel

# Login to Vercel
vercel login

# Deploy (from the frontend folder)
cd frontend
vercel

# Follow the prompts:
# - Set up and deploy? Yes
# - Which scope? [Select your account]
# - Link to existing project? No
# - What's your project's name? fcrules-frontend
# - In which directory is your code located? ./
# - Want to override settings? No

# Your frontend will be deployed to a preview URL

# For production deployment
vercel --prod
```

### Step 4: Test Your Deployment

Once deployed, you'll get a URL like:
```
https://fcrules-frontend.vercel.app
```

**Test these features:**

1. ✅ **Page loads** - You see the pitch-themed UI
2. ✅ **Stats load** - Numbers appear in the header (17 Laws, All-Time Questions)
3. ✅ **Ask a question** - Try: "What is offside?"
4. ✅ **Get response** - AI responds with formatted answer
5. ✅ **Evidence panel** - Click "Sources" to see citations
6. ✅ **Suggestions work** - Click pre-made questions

### Step 5: Verify Backend Connection

Open browser console (F12) and check:
- No CORS errors
- API calls to `https://fcrules.vercel.app/ask` succeed
- Responses are properly formatted

## 🔧 Customization

### Change Backend URL

If you deploy your backend to a different URL:

1. **Edit `index.html`** line 962-965:
   ```javascript
   const API_BASE = () => {
     const val = document.getElementById('api-url-input')?.value.replace(/\/$/, '');
     return val || 'https://YOUR-NEW-BACKEND.vercel.app';
   };
   ```

2. **Redeploy**:
   ```bash
   git add index.html
   git commit -m "Update backend URL"
   git push
   ```
   
   Vercel will auto-deploy the update!

### Custom Domain (Optional)

1. Go to your Vercel project settings
2. Navigate to "Domains"
3. Add your custom domain (e.g., `footballlaw.com`)
4. Follow DNS configuration instructions
5. Wait for DNS propagation (5-30 minutes)

## 📊 Project URLs

After deployment, you'll have:

| Service | URL |
|---------|-----|
| **Frontend** | `https://fcrules-frontend.vercel.app` |
| **Backend API** | `https://fcrules.vercel.app` |
| **API Health** | `https://fcrules.vercel.app/health` |
| **API Stats** | `https://fcrules.vercel.app/stats` |

## 🎨 File Structure

```
fcrules-frontend/
├── index.html          ← Main application (everything in one file!)
├── vercel.json         ← Vercel configuration
├── README.md           ← Documentation
├── .gitignore          ← Git ignore rules
└── DEPLOYMENT_GUIDE.md ← This file
```

## ✅ Deployment Checklist

Before going live, verify:

- [ ] Backend is healthy: `https://fcrules.vercel.app/health`
- [ ] Frontend loads without errors
- [ ] Stats display correctly (17 laws, query count)
- [ ] Questions return proper answers
- [ ] Evidence panel shows citations
- [ ] Mobile view works correctly
- [ ] All suggestion buttons work
- [ ] No console errors in browser

## 🐛 Common Issues

### Issue: Stats showing "—" (dashes)

**Cause**: Backend not responding or CORS error

**Solution**:
1. Check backend health: `https://fcrules.vercel.app/health`
2. Verify CORS is enabled in backend
3. Check browser console for errors

### Issue: "Could not connect to API" error

**Cause**: Network error or wrong API URL

**Solution**:
1. Verify backend URL in code is correct
2. Test API directly: `curl https://fcrules.vercel.app/health`
3. Check for typos in URL

### Issue: Changes not appearing after push

**Cause**: Browser cache or deployment delay

**Solution**:
1. Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
2. Check Vercel deployment logs
3. Wait 1-2 minutes for deployment to complete

### Issue: Questions taking too long

**Cause**: Backend cold start

**Solution**:
- First request may take 10-15 seconds
- Subsequent requests will be faster
- This is normal for serverless functions

## 🚀 Automatic Deployments

Vercel automatically deploys when you push to GitHub:

```bash
# Make changes to index.html
# Commit and push
git add .
git commit -m "Update UI colors"
git push

# Vercel automatically:
# 1. Detects the push
# 2. Builds and deploys
# 3. Updates the live site
# 4. Notifies you via email
```

## 📈 Monitoring

Monitor your deployment:

1. **Vercel Dashboard**
   - Visit: https://vercel.com/dashboard
   - Click your project
   - View: Deployments, Analytics, Logs

2. **Analytics** (if enabled)
   - Page views
   - Unique visitors
   - Performance metrics

3. **Real User Monitoring**
   - Check "All-Time Questions" stat
   - Monitor response times
   - Track user engagement

## 🎉 Success!

You now have:
- ✅ Beautiful frontend deployed
- ✅ Connected to your RAG backend
- ✅ Auto-deployments on git push
- ✅ Free hosting on Vercel
- ✅ HTTPS enabled automatically

**Share your URL and enjoy!** ⚽

---

## 📞 Need Help?

- **Vercel Docs**: https://vercel.com/docs
- **Vercel Support**: https://vercel.com/support
- **GitHub Issues**: Create an issue in your repo
