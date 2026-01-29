# DHB Historical Analysis

A Critical Examination of Democratic Policy Impacts

## Project Structure

```
DHB/
├── public/              # Static site files (deployed to Netlify)
│   ├── index.html       # Main HTML file
│   ├── styles.css       # Stylesheet
│   ├── script.js        # JavaScript
│   └── assets/          # Images, fonts, etc.
├── .gitignore           # Git ignore rules
├── netlify.toml         # Netlify configuration
├── package.json         # Project metadata & scripts
└── README.md            # This file
```

## Development

Run locally:
```bash
npm start
```

This will start a local server at http://localhost:3000

## Deployment

### Deploy to Netlify

1. **Connect to GitHub:**
   - Create a new repository on GitHub
   - Push your code:
     ```bash
     git add .
     git commit -m "Initial commit"
     git branch -M main
     git remote add origin https://github.com/YOUR_USERNAME/DHB.git
     git push -u origin main
     ```

2. **Deploy on Netlify:**
   - Go to [Netlify](https://app.netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Choose GitHub and select your DHB repository
   - Netlify will auto-detect settings from `netlify.toml`
   - Click "Deploy site"

### Manual Deploy

If you have Netlify CLI installed:
```bash
npm run deploy
```

## Configuration

The `netlify.toml` file specifies:
- **Publish directory:** `public/` - contains all static files
- **Build command:** None needed (static site)
- **Redirects:** SPA redirect for client-side routing

## License

All rights reserved.
