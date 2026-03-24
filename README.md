# RE Teamup Website

Verified contractor network for real estate investors.

## Structure

- `/` - Homepage
- `/claim/` - Claim page (reads business_slug from URL path)

## Deployment

This site is configured for GitHub Pages deployment.

### Local Testing

```bash
npx serve .
```

### Deploy to GitHub Pages

1. Create repo on GitHub: `genix6dao/re-teamup`
2. Push this directory to `gh-pages` branch
3. Enable GitHub Pages in repo settings
4. Site will be live at: https://genix6dao.github.io/re-teamup/

## Claim Page URL Format

The claim page expects URLs in this format:
```
https://re-teamup.genix6.com/claim/{business_slug}
```

The business_slug is extracted from the URL path and used to fetch the business profile from Supabase.

## Supabase Integration

The claim page connects directly to Supabase using the JavaScript client library:
- Fetches contact data by business_slug
- Updates stage to 'claimed' on form submission
- Stores claim metadata (name, email, timestamp)