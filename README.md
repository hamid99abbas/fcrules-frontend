# FootballLaw Frontend - Vercel Deployment

Beautiful AI-powered Football Laws of the Game interface.

## 🎨 Features

- **Modern Pitch-Themed UI** - Inspired by football pitch aesthetics
- **Real-time AI Answers** - Powered by your RAG backend
- **Smart Evidence Display** - Shows law citations and sources
- **Session Statistics** - Tracks questions asked
- **Responsive Design** - Works on all devices
- **Quick Suggestions** - Common question templates

## 🚀 Quick Deployment

### Option 1: Deploy via Vercel Dashboard (Recommended)

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin your-repo-url
   git push -u origin main
   ```

2. **Import in Vercel**
   - Go to [vercel.com/new](https://vercel.com/new)
   - Import your repository
   - Vercel will auto-detect the configuration
   - Click "Deploy"

### Option 2: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
cd frontend
vercel

# For production
vercel --prod
```

## 🔗 Backend Connection

The frontend is pre-configured to connect to your backend API:
```
Backend API: https://fcrules.vercel.app
```

If you need to change the backend URL, users can update it in the settings panel within the app.

## 📁 Project Structure

```
frontend/
├── index.html        # Main application file
├── vercel.json       # Vercel configuration
└── README.md         # This file
```

## ⚙️ Configuration

The app automatically connects to `https://fcrules.vercel.app` by default.

To use a different backend URL:
1. Open the app in a browser
2. Look for the API URL input in the settings/footer
3. Enter your custom backend URL
4. Refresh the page

## 🎯 Testing Locally

Simply open `index.html` in any modern browser:
```bash
# On macOS
open index.html

# On Windows
start index.html

# On Linux
xdg-open index.html

# Or use a simple HTTP server
python -m http.server 8000
# Then visit: http://localhost:8000
```

## 📊 Features Breakdown

### Main Interface
- **Hero Section** - Title, badge, and statistics
- **Chat Area** - Message history with AI responses
- **Input Field** - Auto-resizing textarea with Enter to send
- **Suggestions** - Pre-made questions to get started

### AI Response Display
- **Law Tags** - Highlighted law numbers
- **Formatted Answers** - Structured with Decision/Restart/Discipline
- **Evidence Panel** - Collapsible sources with citations
- **Performance Metrics** - Response time badges
- **Card Highlights** - Yellow/Red card mentions

### Settings
- **Show Evidence** - Toggle citation display
- **Include Raw Chunks** - Show full text from sources (advanced)
- **Custom API URL** - Override default backend

## 🎨 Design System

### Colors
- **Pitch Dark**: Deep green background
- **Line White**: Text and borders
- **Lime/Bright**: Accent colors
- **Yellow/Red**: Card colors
- **Gradient Effects**: Subtle overlays

### Typography
- **Display**: Bebas Neue (headers)
- **Body**: DM Sans (text)
- **Mono**: JetBrains Mono (technical elements)

### Effects
- **Pitch Stripes**: Animated background
- **Corner Flags**: Decorative elements
- **Grain Texture**: Subtle noise overlay
- **Glow Effects**: Law tags and accents

## 🔍 API Integration

The frontend makes these API calls:

```javascript
// Get statistics
GET https://fcrules.vercel.app/stats

// Ask a question
POST https://fcrules.vercel.app/ask
{
  "question": "What is offside?",
  "top_k": 10,
  "include_raw_chunks": false
}
```

## 📱 Responsive Design

- **Desktop**: Full layout with all features
- **Tablet**: Optimized spacing and typography
- **Mobile**: Touch-friendly with adjusted sizing

## 🐛 Troubleshooting

### "Could not connect to API" error
- Check that backend is deployed and healthy
- Visit `https://fcrules.vercel.app/health` to verify
- Check browser console for CORS errors

### Stats not loading
- Backend may be cold-starting (wait 5 seconds)
- Verify `/stats` endpoint is accessible

### Typing indicator stuck
- Refresh the page
- Check network tab for failed requests

## 🚀 Deployment Checklist

- [ ] Backend API is deployed and healthy
- [ ] Frontend code pushed to Git repository
- [ ] Vercel project created and linked
- [ ] DNS configured (if using custom domain)
- [ ] Test all features after deployment
- [ ] Monitor for errors in Vercel dashboard

## 📈 Future Enhancements

Potential improvements:
- [ ] Dark/light theme toggle
- [ ] Question history persistence
- [ ] Bookmark favorite laws
- [ ] Share conversation links
- [ ] Multi-language support
- [ ] Voice input
- [ ] PDF export of conversations

## 🔗 Links

- **Backend API**: https://fcrules.vercel.app
- **Backend Health**: https://fcrules.vercel.app/health
- **Backend Stats**: https://fcrules.vercel.app/stats
- **Vercel Docs**: https://vercel.com/docs

## 📝 Notes

- The app is a single HTML file with embedded CSS and JavaScript
- No build process required
- Works entirely client-side
- All AI processing happens on the backend
- Fonts loaded from Google Fonts CDN

---

Built with ⚽ for football enthusiasts and referees everywhere.
