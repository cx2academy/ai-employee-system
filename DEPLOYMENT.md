# Deployment Guide 🚀

This guide will walk you through deploying your AI Employee System to the web in under 10 minutes.

## Option 1: Vercel (Easiest & Recommended) ✅

Vercel is the fastest way to deploy. Free tier is more than enough.

### Step-by-Step:

1. **Push your code to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/ai-employee-system.git
   git push -u origin main
   ```

2. **Go to Vercel**
   - Visit [vercel.com](https://vercel.com)
   - Sign up with your GitHub account (free)

3. **Import Project**
   - Click "Add New..." → "Project"
   - Click "Import" next to your repository
   - Vercel auto-detects everything - no configuration needed!

4. **Deploy**
   - Click "Deploy"
   - Wait 1-2 minutes
   - Your site is live! You'll get a URL like `your-project.vercel.app`

5. **Custom Domain (Optional)**
   - Go to Project Settings → Domains
   - Add your custom domain
   - Follow DNS instructions

**That's it!** Every time you push to GitHub, Vercel automatically redeploys.

**⚠️ IMPORTANT:** The project is now configured to work with Vercel by default. No changes needed!

---

## Option 2: Netlify

Another excellent free option with drag-and-drop support.

### Step-by-Step:

1. **Push to GitHub** (same as Vercel step 1)

2. **Go to Netlify**
   - Visit [netlify.com](https://netlify.com)
   - Sign up with GitHub

3. **Import Project**
   - Click "Add new site" → "Import an existing project"
   - Choose GitHub and select your repository

4. **Configure Build**
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Click "Deploy site"

5. **Get Your URL**
   - Site is live at `random-name.netlify.app`
   - Change site name in Settings → Site details

**Alternatively - Drag & Drop:**
1. Run `npm run build` locally
2. Go to Netlify
3. Drag the `dist` folder onto the deploy area
4. Instant deploy!

---

## Option 3: GitHub Pages

Free hosting directly from your GitHub repository.

### Step-by-Step:

1. **Install gh-pages**
   ```bash
   npm install -D gh-pages
   ```

2. **Update package.json**
   Add these scripts:
   ```json
   "scripts": {
     "predeploy": "npm run build",
     "deploy": "gh-pages -d dist"
   }
   ```

3. **Add homepage field**
   In package.json, add:
   ```json
   "homepage": "https://yourusername.github.io/ai-employee-system"
   ```

4. **Deploy**
   ```bash
   npm run deploy
   ```

5. **Enable GitHub Pages**
   - Go to your repo on GitHub
   - Settings → Pages
   - Source: Deploy from branch `gh-pages`
   - Wait 1-2 minutes

Your site is live at `https://yourusername.github.io/ai-employee-system`

---

## Option 4: Railway

Great for projects that might need backend features later.

### Step-by-Step:

1. **Push to GitHub** (same as above)

2. **Go to Railway**
   - Visit [railway.app](https://railway.app)
   - Sign up with GitHub

3. **Create New Project**
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Choose your repository

4. **Configure**
   - Railway auto-detects Vite
   - Add environment variables if needed

5. **Deploy**
   - Automatic deployment starts
   - Get your URL from the deployment tab

---

## Post-Deployment Checklist

After deploying to any platform:

✅ **Test the onboarding flow**
   - Complete all 11 questions
   - Verify data saves correctly

✅ **Test each AI employee**
   - Open each employee
   - Send a test message
   - Verify responses work

✅ **Check mobile responsiveness**
   - Open on phone/tablet
   - Ensure UI looks good

✅ **Test data persistence**
   - Complete onboarding
   - Close browser
   - Reopen - verify data is still there

---

## Troubleshooting

### "404 Not Found" on refresh
**Solution for Netlify:**
Create `public/_redirects` file:
```
/*    /index.html   200
```

**Solution for Vercel:**
Already handled by `vercel.json`!

### API calls failing
- Check browser console for CORS errors
- Verify API endpoint is correct
- Check if API key is needed for standalone deployment

### Build fails
```bash
# Clear everything and reinstall
rm -rf node_modules package-lock.json dist
npm install
npm run build
```

---

## Custom Domain Setup

### Vercel
1. Project Settings → Domains
2. Add your domain (e.g., `myaiemployees.com`)
3. Update DNS records at your registrar:
   - Add A record or CNAME as instructed
4. Wait for DNS propagation (5-30 minutes)

### Netlify
1. Domain settings → Add custom domain
2. Follow DNS instructions
3. Netlify provides free SSL certificate automatically

---

## Environment Variables (For Production)

If you want to secure your API key:

1. **Create backend proxy** (recommended for production)
2. **Set environment variable** in your deployment platform:
   - Vercel: Settings → Environment Variables
   - Netlify: Site settings → Environment variables
   - Add: `VITE_ANTHROPIC_API_KEY=your-key-here`

3. **Update code** to use env variable:
   ```javascript
   const apiKey = import.meta.env.VITE_ANTHROPIC_API_KEY;
   ```

---

## Cost Breakdown

All platforms have generous free tiers:

- **Vercel**: Free for hobby projects, unlimited bandwidth
- **Netlify**: 100GB bandwidth/month free
- **GitHub Pages**: Free, unlimited static sites
- **Railway**: $5/month free credit

**API Costs** (Anthropic):
- Claude Sonnet 4: ~$3 per million input tokens
- Typical usage: $10-50/month for active business

---

## Need Help?

1. Check the main [README.md](README.md)
2. Open an issue on GitHub
3. Check deployment platform's documentation

**Ready to scale your business with AI? Let's go! 🚀**
