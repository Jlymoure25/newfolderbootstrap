# What's The Happenings Around Town

A Bootstrap-based web project for showcasing and registering community events.

## Features

- **Responsive Navbar:** Includes Home, About, Contact, and Register links with a hamburger menu for mobile.
- **Video Banner:** Eye-catching video banner with overlayed heading.
- **Circular Logo:** Centered, shadowed circular logo.
- **Events Gallery:** 2x2 grid of event images/videos, all centered and responsive.
- **Registration Form:** Users can register for events with validation and terms checkbox.
- **Submitted Users Table:** Displays sample registered users.
- **Manual Video Playback:** Videos require user interaction to play with sound.

## File Structure

- `public/index.html` — Main homepage
- `public/About-What's the Happening.html` — About page
- `public/contact What's The Happenings-1.html` — Contact page
- `public/register-2what's the happening.html` — Registration page fragment
- Images and videos are in the public directory

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the local server:
   ```bash
   npm start
   ```

3. Open your browser and navigate to `http://localhost:3000`

## Deployment to Netlify

### Option 1: Deploy via Netlify UI

1. Log in to [Netlify](https://netlify.com)
2. Click "Add new site" → "Import an existing project"
3. Connect your GitHub repository
4. Configure build settings:
   - **Build command:** `npm run build`
   - **Publish directory:** `public`
5. Click "Deploy site"

### Option 2: Deploy via Netlify CLI

1. Install Netlify CLI:
   ```bash
   npm install -g netlify-cli
   ```

2. Login to Netlify:
   ```bash
   netlify login
   ```

3. Deploy the site:
   ```bash
   netlify deploy --prod
   ```

### Configuration

The repository includes a `netlify.toml` file that configures:
- Publish directory: `public`
- Build command: `npm run build`
- Redirects for single-page app behavior

## Requirements

- [Bootstrap 5](https://getbootstrap.com/) (loaded via CDN)
- Modern web browser
- Node.js (for local development)

## Customization

- **Images/Videos:** Replace image and video files in the `public` directory
- **Colors/Branding:** Adjust Bootstrap classes or add custom CSS
- **Links:** Update navbar and button links as needed

---

© 2025 What's The Happenings Around Town
