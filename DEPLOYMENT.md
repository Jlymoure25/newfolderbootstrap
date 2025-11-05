# Netlify Deployment Guide

This guide provides step-by-step instructions for deploying the "What's The Happenings Around Town" website to Netlify.

## Prerequisites

- A GitHub account (this repository)
- A [Netlify account](https://app.netlify.com/signup) (free tier is sufficient)

## Deployment Methods

### Method 1: Deploy via Netlify UI (Recommended for Beginners)

1. **Sign in to Netlify**
   - Go to [https://app.netlify.com](https://app.netlify.com)
   - Sign in with your GitHub account (recommended) or create an account

2. **Create a New Site**
   - Click the "Add new site" button
   - Select "Import an existing project"

3. **Connect to GitHub**
   - Choose "Deploy with GitHub"
   - Authorize Netlify to access your repositories if prompted
   - Search for and select the `Jlymoure25/newfolderbootstrap` repository

4. **Configure Build Settings**
   - **Site name:** Choose a custom name (e.g., `whats-happening-around-town`) or use the auto-generated one
   - **Branch to deploy:** `copilot/deploy-to-netlify` (or `main` if merged)
   - **Build command:** `npm run build`
   - **Publish directory:** `public`
   
   These settings should be auto-detected from the `netlify.toml` file.

5. **Deploy**
   - Click "Deploy site"
   - Wait for the deployment to complete (usually takes 1-2 minutes)
   - Your site will be live at `https://[your-site-name].netlify.app`

6. **Custom Domain (Optional)**
   - Go to "Site settings" → "Domain management"
   - Click "Add custom domain" to use your own domain name

### Method 2: Deploy via Netlify CLI (For Developers)

1. **Install Netlify CLI**
   ```bash
   npm install -g netlify-cli
   ```

2. **Login to Netlify**
   ```bash
   netlify login
   ```
   This will open a browser window for authentication.

3. **Initialize and Deploy**
   ```bash
   # Navigate to the project directory
   cd /path/to/newfolderbootstrap
   
   # Deploy to production
   netlify deploy --prod
   ```

4. **Follow the Prompts**
   - Choose "Create & configure a new site"
   - Select your team
   - Enter a site name (optional)
   - For publish directory, enter: `public`

5. **View Your Site**
   - The CLI will display your live site URL

### Method 3: Drag and Drop Deploy

1. **Build Locally**
   ```bash
   npm install
   npm run build
   ```

2. **Deploy via Netlify UI**
   - Go to [https://app.netlify.com/drop](https://app.netlify.com/drop)
   - Drag and drop the `public` folder
   - Your site will be deployed instantly

## Configuration Files

The repository includes the following configuration files for Netlify:

- **`netlify.toml`** - Main Netlify configuration file
  - Sets publish directory to `public`
  - Defines build command
  - Configures redirects for SPA behavior

- **`public/_redirects`** - Netlify redirects file
  - Ensures all routes serve index.html

- **`package.json`** - Node.js dependencies and scripts
  - `npm run build` - Build command (no actual build needed for static site)
  - `npm start` - Local development server

## Environment Variables (If Needed)

If you need to add environment variables:

1. Go to "Site settings" → "Build & deploy" → "Environment"
2. Click "Edit variables"
3. Add your key-value pairs

## Continuous Deployment

Once connected to GitHub, Netlify will automatically:
- Deploy every push to the connected branch
- Create deploy previews for pull requests
- Show deployment status in GitHub

## Post-Deployment Checklist

- [ ] Verify the site loads at your Netlify URL
- [ ] Test all navigation links (Home, About, Contact, Register)
- [ ] Check that images load correctly
- [ ] Verify videos play properly
- [ ] Test the registration form
- [ ] Check mobile responsiveness
- [ ] Test on different browsers

## Troubleshooting

### Site Not Loading
- Check that publish directory is set to `public`
- Verify build command completed successfully in deploy logs

### Images/Videos Not Loading
- Ensure all file paths are relative (not absolute Windows paths)
- Check that files exist in the `public` directory
- Verify file names match exactly (case-sensitive)

### Build Failures
- Check the deploy log in Netlify dashboard
- Verify `package.json` dependencies are correct
- Ensure Node.js version is compatible (v14+ recommended)

### 404 Errors on Page Refresh
- Verify `_redirects` file exists in `public` directory
- Check `netlify.toml` redirect configuration

## Support

For Netlify-specific issues:
- [Netlify Documentation](https://docs.netlify.com/)
- [Netlify Support Forums](https://answers.netlify.com/)

For repository issues:
- Open an issue on GitHub

## Site URLs

After deployment, your site will be available at:
- **Netlify URL:** `https://[your-site-name].netlify.app`
- **Custom Domain:** Configure in Netlify dashboard (optional)

---

Happy Deploying! 🚀
