# BoxFort SLA Dashboard - Deployment Guide

## Option 1: Deploy via Vercel CLI (Fastest)

1. **Install Vercel CLI** (if not already):
   ```bash
   npm install -g vercel
   ```

2. **Unzip and navigate**:
   ```bash
   unzip sla-dashboard.zip
   cd sla-dashboard
   ```

3. **Install dependencies**:
   ```bash
   npm install
   ```

4. **Deploy**:
   ```bash
   vercel
   ```
   - Follow prompts (accept defaults)
   - First deployment creates project
   - Get your live URL!

5. **For production**:
   ```bash
   vercel --prod
   ```

---

## Option 2: Deploy via Vercel Website

1. **Go to**: https://vercel.com
2. **Log in** (or create account)
3. **Click**: "Add New" → "Project"
4. **Choose**: "Upload" tab
5. **Drag** the `sla-dashboard` folder (unzipped)
6. **Click**: Deploy
7. **Done!** Get your live URL

---

## Option 3: Connect to GitHub (Best for updates)

1. **Create GitHub repo**:
   ```bash
   cd sla-dashboard
   git init
   git add .
   git commit -m "Initial commit"
   gh repo create boxfort-sla-dashboard --public --push
   ```

2. **In Vercel**:
   - Import from GitHub
   - Select the repo
   - Deploy automatically

3. **Future updates**: Just push to GitHub and Vercel auto-deploys

---

## After Deployment

Your dashboard will be live at something like:
`https://boxfort-sla-dashboard.vercel.app`

The dashboard:
- Fetches live data from your Google Sheets
- Auto-refreshes every 5 minutes
- Works on mobile and desktop

## Test It

1. Add a test row to your "Daily Orders" sheet:
   | Date | Order ID | ShipHero ID | Shop Name | Ready At | Shipped At | SLA Met |
   |------|----------|-------------|-----------|----------|------------|---------|
   | 2024-12-30 | TEST-001 | xyz123 | tiny-rituals.myshopify.com | 09:00 | 14:30 | YES |

2. Wait 1-2 minutes (Google Sheets publish cache)
3. Refresh your dashboard

---

## Custom Domain (Optional)

In Vercel dashboard:
1. Go to project Settings → Domains
2. Add your domain (e.g., `sla.boxfortcommerce.com`)
3. Update DNS as instructed
