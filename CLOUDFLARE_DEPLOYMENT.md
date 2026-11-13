# Cloudflare Pages Deployment

This application is deployed on **Cloudflare Pages** - a fast, reliable static hosting platform.

## Deployment Configuration

No configuration files are needed. Cloudflare Pages handles everything through the web dashboard.

## Initial Setup (One-time)

1. **Connect your GitHub repository to Cloudflare Pages:**
   - Go to [Cloudflare Pages](https://pages.cloudflare.com/)
   - Click **"Connect to Git"**
   - Authorize GitHub and select the `mfs-solutions/antigrixai` repository
   - Select branch: `main`

2. **Configure build settings:**
   - **Framework preset:** None
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
   - **Root directory:** (leave empty)
   - **Node.js version:** (Auto-detected: 24.18.0)

3. **Environment Variables (if needed):**
   - Add any API keys or configuration in the Pages project settings
   - Example: `API_KEY`, database connection strings, etc.

4. **Deploy:**
   - Click "Save and Deploy"
   - Cloudflare will automatically build and deploy your site

## Automatic Deployments

Every time you push to the `main` branch, Cloudflare Pages will:
1. Clone your repository
2. Run `npm install` to install dependencies
3. Run `npm run build` to generate the `dist` folder
4. Deploy to your Pages domain (e.g., `antigrix-ai.pages.dev`)

## Custom Domain

To use a custom domain:
1. Go to your Cloudflare Pages project settings
2. In **Custom domains**, click **"Set up a custom domain"**
3. Enter your domain (e.g., `antigrix.ai`)
4. Follow the DNS configuration instructions
5. Cloudflare will provide nameservers or DNS records to update

## Build & Deployment Logs

Monitor your deployments:
- Go to Cloudflare Pages project → **Deployments** tab
- Click on any deployment to see build logs
- Failed deployments show error messages and build output

## SPA Routing

The `_redirects` file ensures all requests are routed to `index.html` for proper React Router navigation:
```
/*    /index.html   200
```

This is handled automatically by Cloudflare Pages.

## Troubleshooting

### Build Fails
- Check build logs in Cloudflare Pages **Deployments** tab
- Ensure `npm run build` works locally: `npm run build`
- Verify all dependencies are in `package.json`

### Site Returns 404
- Check that `_redirects` file exists
- Verify build output directory is `dist`
- Test routing locally: `npm run preview`

### Environment Variables Not Working
- Confirm variables are added in Pages project settings
- Redeploy after adding new variables
- Check application code uses `process.env.VARIABLE_NAME`

## Local Preview

Test your build locally before pushing:
```bash
npm run build
npm run preview
```

Then visit http://localhost:4173
