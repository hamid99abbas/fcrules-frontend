# 🎯 QUICK START - 3 Steps to Deploy

## Step 1️⃣: Push to GitHub (2 minutes)

```bash
# Navigate to frontend folder
cd frontend

# Initialize and push
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/fcrules-frontend.git
git push -u origin main
```

**OR use the quick script:**
```bash
chmod +x deploy.sh
./deploy.sh
```

---

## Step 2️⃣: Deploy on Vercel (1 minute)

### Go to: https://vercel.com/new

1. Click "Import Git Repository"
2. Select `fcrules-frontend`
3. Click "Deploy"
4. ✅ Done!

**Your frontend will be live at:**
```
https://fcrules-frontend-xxx.vercel.app
```

---

## Step 3️⃣: Test It! (30 seconds)

Visit your URL and try:

✅ Ask: "What is offside?"  
✅ Click suggestion: "What is the handball rule?"  
✅ Check stats in header  
✅ View sources/evidence  

---

## 🎉 That's It!

Your complete Football Law AI system is now live:

| Component | URL |
|-----------|-----|
| 🎨 **Frontend** | `https://fcrules-frontend.vercel.app` |
| 🔧 **Backend API** | `https://fcrules.vercel.app` |
| ✅ **Health Check** | `https://fcrules.vercel.app/health` |

---

## 🔄 Future Updates

To deploy updates:

```bash
# Make changes to index.html
git add .
git commit -m "Update UI"
git push

# ✅ Vercel auto-deploys!
```

---

## 📞 Need Help?

Check these files:
- `README.md` - Full documentation
- `DEPLOYMENT_GUIDE.md` - Detailed step-by-step
- `deploy.sh` - Automated deployment script

**Common Issues:**
- Stats not loading? → Backend might be cold-starting (wait 10s)
- Questions failing? → Check browser console for errors
- Changes not showing? → Hard refresh (Ctrl+Shift+R)

---

## 🚀 You're Live!

Share your Football Law AI with:
- Football coaches and referees
- Players learning the rules
- Anyone with questions about the Laws of the Game

⚽ Enjoy your deployment!
