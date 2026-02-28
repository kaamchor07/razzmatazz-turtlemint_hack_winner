# Razzmatazz

A modern full-stack platform for insurance agents to manage customer relationships, generate AI-powered content for multiple platforms, and deploy custom websites.

## Features

- **User Authentication** – Sign up and sign in for insurance agents
- **CRM Dashboard** – Manage customer interactions and leads
- **AI Content Generation** – Generate targeted content for:
  - Facebook
  - Instagram
  - LinkedIn
  - X (Twitter)
  - WhatsApp
  - Email/Analytics
- **Website Builder** – Auto-generate professional insurance websites using Gemini AI
- **Vercel Integration** – One-click deployment of generated websites
- **Multi-Platform Management** – Centralized dashboard for all platforms
- **Call Analytics** – Analyze and track call interactions

## Tech Stack

- **Frontend:** Next.js 14, React, TypeScript, Tailwind CSS
- **Backend:** Next.js API Routes
- **Database:** Supabase (PostgreSQL)
- **AI:** Google Gemini API
- **Authentication:** Supabase Auth
- **Deployment:** Vercel API
- **Styling:** PostCSS, Tailwind CSS

## Prerequisites

- Node.js 18+ and npm/yarn/pnpm
- A Supabase account and project
- A Google Gemini API key
- A Vercel account and token (for deployment features)

## Getting Started

### 1. Clone and Install

```bash
git clone <repository-url>
cd Razzmataz
npm install
```

### 2. Set Up Environment Variables

Copy the example environment file and add your credentials:

```bash
cp .env.example .env.local
```

Then edit `.env.local` and fill in your keys:

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key

# Google Gemini
NEXT_PUBLIC_GEMINI_API_KEY=your_gemini_api_key

# Vercel Deployment
NEXT_PUBLIC_VERCEL_TOKEN=your_vercel_token
```

**Important:** Never commit `.env.local` to version control. See [Security](#security) below.

### 3. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### 4. Build for Production

```bash
npm run build
npm start
```

## Project Structure

```
src/
├── app/                      # Next.js app directory
│   ├── api/                  # API routes for backend services
│   │   ├── analyze-call/
│   │   ├── facebook-content/
│   │   ├── generate-website/
│   │   ├── instagram-content/
│   │   ├── linkedin-content/
│   │   ├── whatsapp-content/
│   │   └── x-content/
│   ├── auth/                 # Authentication pages
│   │   ├── signin/
│   │   └── signup/
│   ├── crm/                  # CRM dashboard
│   ├── dashboard/            # Main dashboard
│   ├── facebook/             # Facebook integration
│   ├── instagram/            # Instagram integration
│   ├── linkedin/             # LinkedIn integration
│   ├── website-builder/      # Website builder
│   ├── whatsapp/             # WhatsApp integration
│   ├── x/                    # X (Twitter) integration
│   ├── interaction/          # Interaction tracking
│   ├── layout.tsx            # Root layout
│   ├── page.tsx              # Home page
│   └── globals.css           # Global styles
├── contexts/                 # React Context providers
│   └── AuthContext.tsx       # Authentication state
├── lib/                      # Utility libraries
│   ├── gemini.ts             # Gemini AI integration
│   ├── supabase.ts           # Supabase client & helpers
│   └── vercel.ts             # Vercel deployment API
└── public/                   # Static assets
    └── assets/
```

## Security

⚠️ **NEVER commit real API keys or tokens to the repository.**

- Use `.env.local` for local development (ignored by `.gitignore`)
- Use `.env.example` as a template for required variables
- For production, set environment variables in your deployment platform (Vercel, etc.)
- **If you accidentally commit secrets:**
  - Rotate the keys immediately
  - Use `git-filter-repo` or `BFG Repo-Cleaner` to remove them from history
  - Force push the cleaned history

## API Endpoints

### Content Generation

- `POST /api/facebook-content` – Generate Facebook content
- `POST /api/instagram-content` – Generate Instagram content
- `POST /api/linkedin-content` – Generate LinkedIn content
- `POST /api/x-content` – Generate X (Twitter) content
- `POST /api/whatsapp-content` – Generate WhatsApp messages

### Website Builder

- `POST /api/generate-website` – Generate an insurance website using Gemini AI

### Analytics

- `POST /api/analyze-call` – Analyze call interactions

## Development Tips

- Hot reload is enabled; changes to `.tsx` files automatically refresh the browser
- Use the browser's React Developer Tools for debugging components
- Check terminal logs for API errors and warnings

## Deployment

### Deploy on Vercel

The easiest way to deploy is using the [Vercel Platform](https://vercel.com):

1. Push your code to GitHub
2. Import the repository in Vercel
3. Add environment variables in the Vercel dashboard
4. Deploy with a single click

See [Next.js Deployment Documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

## Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [Supabase Documentation](https://supabase.com/docs)
- [Google Gemini API](https://ai.google.dev/)
- [Vercel API Documentation](https://vercel.com/docs/api)

## License

This project is proprietary. All rights reserved.
