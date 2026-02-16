# AI Employee System 🚀

A complete AI-powered employee system that learns your business and handles content strategy, copywriting, video planning, ads, email marketing, growth analytics, community management, and sales strategy.

## Features

✅ **8 AI Employees** - Each specialized in a different role  
✅ **Smart Onboarding** - 11 questions to understand any business  
✅ **Persistent Memory** - Saves your business context and conversations  
✅ **Powered by Claude Sonnet 4** - Each employee uses advanced AI  
✅ **Universal Application** - Works for any online business, course, or coaching program

## AI Employees Included

1. **Content Strategist** - Creates content calendars, hooks, and messaging strategy
2. **Copywriter** - Writes captions, emails, sales copy, and scripts
3. **Video Strategist** - Plans video concepts, scripts, and repurposing strategy
4. **Ads Manager** - Creates ad strategies, targeting, and copy variations
5. **Email Marketer** - Builds email sequences, broadcasts, and nurture campaigns
6. **Growth Analyst** - Analyzes performance and provides optimization insights
7. **Community Manager** - Manages engagement, responses, and community building
8. **Sales Strategist** - Creates sales scripts, objection handlers, and conversion strategies

## Quick Start

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/ai-employee-system.git

# Navigate to project directory
cd ai-employee-system

# Install dependencies
npm install

# Start development server
npm run dev
```

The app will be available at `http://localhost:5173`

## Deployment

### Deploy to Vercel (Recommended)

1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will auto-detect Vite and configure everything
6. Click "Deploy"

Your site will be live in seconds!

### Deploy to Netlify

1. Push your code to GitHub
2. Go to [netlify.com](https://netlify.com)
3. Click "Add new site" → "Import an existing project"
4. Connect to GitHub and select your repository
5. Build settings:
   - Build command: `npm run build`
   - Publish directory: `dist`
6. Click "Deploy site"

### Deploy to GitHub Pages

```bash
# Install gh-pages
npm install -D gh-pages

# Add to package.json scripts:
"predeploy": "npm run build",
"deploy": "gh-pages -d dist"

# Deploy
npm run deploy
```

## How It Works

### 1. Onboarding
The system asks 11 strategic questions to understand:
- Your business name and offer
- Your target audience
- Your unique value proposition
- Your brand voice
- Your platforms and goals

### 2. Business Context Storage
All your answers are saved using browser storage (localStorage fallback) so you never have to re-enter information.

### 3. AI Employees
Each employee has a specialized system prompt that includes:
- Your full business context
- Role-specific expertise and frameworks
- Strategic guidance based on your goals

### 4. Chat Interface
Simply select an employee and give them tasks:
- "Create a 30-day content calendar"
- "Write 5 ad variations for testing"
- "Build a welcome email sequence"
- "Give me 10 viral video ideas"

## API Configuration

The system uses the Anthropic Claude API. The API calls are made client-side and no API key is needed in the claude.ai artifact environment.

**If deploying independently**, you'll need to:
1. Get an API key from [Anthropic](https://console.anthropic.com)
2. Add it to the fetch request in `App.jsx` (line ~384)
3. **Important**: For production, use a backend proxy to keep your API key secure

## Customization

### Add More Employees

Edit the `aiEmployees` array in `App.jsx`:

```javascript
{
  id: 'new-employee',
  name: 'Employee Name',
  icon: IconComponent,
  description: 'What they do',
  color: 'bg-color-500'
}
```

Then add their system prompt in `buildEmployeeSystemPrompt()`.

### Modify Onboarding Questions

Edit the `onboardingQuestions` array in `App.jsx` to add/remove/modify questions.

### Change Styling

The project uses Tailwind CSS. Modify classes in JSX or extend the theme in `tailwind.config.js`.

## Tech Stack

- **React 18** - UI framework
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Styling
- **Lucide React** - Icons
- **Claude Sonnet 4 API** - AI brain for all employees

## Browser Support

- Chrome/Edge (recommended)
- Firefox
- Safari
- Any modern browser with localStorage support

## Storage

The app uses:
1. `window.storage` API (when available in claude.ai)
2. `localStorage` (fallback for standalone deployments)

All data is stored locally in the browser - no external database needed.

## Troubleshooting

### "Error calling AI employee"
- Check your internet connection
- Verify the API is accessible
- Check browser console for specific errors

### Data not persisting
- Make sure cookies/localStorage aren't blocked
- Try a different browser
- Check browser privacy settings

### Build errors
```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

## License

MIT License - feel free to use this for your business!

## Support

For issues or questions, open an issue on GitHub.

---

**Built with ❤️ for entrepreneurs who want to scale without burning out**
