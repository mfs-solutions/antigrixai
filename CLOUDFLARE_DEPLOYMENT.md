# Cloudflare Pages Configuration

This file ensures your React SPA (Single Page Application) works correctly with Cloudflare Pages.

## Configuration

The `wrangler.toml` file configures:
- Build command: `npm run build` generates the `dist` folder
- Root directory: Cloudflare Pages serves content from `dist/`
- Routing: All requests are handled by `index.html` for client-side routing

## Deployment

To deploy to Cloudflare Pages:

1. **Connect your GitHub repository:**
   - Go to [Cloudflare Pages](https://pages.cloudflare.com/)
   - Click "Connect to Git"
   - Authorize GitHub and select your repository
   - Choose the `main` branch

2. **Configure build settings:**
   - Framework preset: None (use custom)
   - Build command: `npm run build`
   - Build output directory: `dist`

3. **Environment variables (if needed):**
   - Add any API keys or configuration in the Pages project settings

4. **Deploy:**
   - Cloudflare Pages will automatically build and deploy on every push to `main`

## Custom Domain

To use a custom domain:
1. Go to your Cloudflare Pages project settings
2. Add your custom domain
3. Update DNS records as instructed by Cloudflare
