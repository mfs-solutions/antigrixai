<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://github.com/user-attachments/assets/0aa67016-6eaf-458a-adb2-6e31a0763ed6" />
</div>

# Run and deploy your app

This contains everything you need to run your app locally and deploy to Cloudflare Pages.

## Run Locally

**Prerequisites:** Node.js

1. Install dependencies:
   ```bash
   npm install
   ```
2. Set your API key in [.env.local](.env.local)
3. Run the app:
   ```bash
   npm run dev
   ```

## Deployment to Cloudflare Pages

This application is deployed on **Cloudflare Pages**. See [CLOUDFLARE_DEPLOYMENT.md](./CLOUDFLARE_DEPLOYMENT.md) for detailed deployment instructions.

### Quick Setup

1. Connect your GitHub repository to [Cloudflare Pages](https://pages.cloudflare.com/)
2. Use these build settings:
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
3. Cloudflare Pages will automatically deploy on every push to `main`
