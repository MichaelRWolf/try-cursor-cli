# Try Cursor CLI (i.e. cursor-agent(1))

## Project Goals
Understand how cursor(1) and cursor-agent(1) can work together to create a complete development workflow for web application projects.

## Project Setup

### Installing cursor-agent
```bash
# Install cursor-agent globally
npm install -g @cursor/agent

# Or install locally in project
npm install @cursor/agent

# Verify installation
cursor-agent --version
```

### Original Website Reference
- **Source Website:** https://www.upsoilandsoul.com/
- **Project Goal:** Complete rewrite of the Upsoil & Soul Farm & Campground website

## Running & Installing Project

### Running the Website Locally

#### Development Server
```bash
# Navigate to the Next.js project directory
cd upsoil-soul-nextjs

# Install dependencies (if not already done)
npm install

# Start the development server
npm run dev
```

#### Access the Website
- **Local Development:** http://localhost:3000
- **Alternative Port:** http://localhost:3001 (if port 3000 is in use)
- **Network Access:** http://192.168.1.144:3000 (accessible from other devices on your network)

#### Debugging the Site
```bash
# Check if the server is running
curl -I http://localhost:3000

# View development logs
# The terminal will show compilation status and any errors

# Hot reloading is enabled - changes to files will automatically refresh the browser
```

#### Production Build (Optional)
```bash
# Create optimized production build
npm run build

# Start production server
npm start
```

### Technology Stacks

#### Original Tech Stack
- **Frontend:** Vanilla HTML5, CSS3, JavaScript (ES6+)
- **Styling:** Custom CSS with Flexbox/Grid, Google Fonts (Inter)
- **Icons:** Font Awesome 6.0.0
- **Images:** Unsplash CDN
- **Responsive:** Mobile-first design with media queries
- **Performance:** Lazy loading, intersection observers, optimized animations

#### Target Tech Stack
- **Framework:** Next.js 15.5.4 with App Router
- **Language:** TypeScript for type safety
- **Styling:** Tailwind CSS for utility-first styling
- **Fonts:** Inter font family via Google Fonts
- **Images:** Next.js Image optimization + Unsplash integration
- **Deployment:** Vercel-ready with static generation
- **Performance:** Built-in optimizations, code splitting, and Core Web Vitals

##### Improvements
**For Developers:**
- **Type Safety:** TypeScript catches errors at compile time, reducing runtime bugs
- **Component Architecture:** Reusable React components improve code organization
- **Hot Reloading:** Instant feedback during development with Next.js dev server
- **Built-in Tooling:** ESLint, TypeScript, and build optimizations out of the box
- **Modern Development:** Latest React patterns, hooks, and best practices

**For Human Users:**
- **Faster Loading:** Static generation and image optimization improve page speed
- **Better SEO:** Server-side rendering improves search engine visibility
- **Mobile Experience:** Responsive design with Tailwind's mobile-first approach
- **Accessibility:** Better semantic HTML and ARIA support
- **Progressive Enhancement:** Works without JavaScript, enhanced with it

**For Business/Operations:**
- **Deployment:** One-click deployment to Vercel with automatic builds
- **Scalability:** Static generation handles high traffic efficiently
- **Maintenance:** Component-based architecture makes updates easier
- **Performance:** Core Web Vitals optimization improves user experience metrics
- **Cost Efficiency:** Static hosting is more cost-effective than server-side rendering

## Project Tasks

### Original Development Todos (11 Tasks Completed)

1. **Parse web page content** from https://www.upsoilandsoul.com/ and extract all text, images, and structural elements
2. **Analyze parsed content structure** and identify main sections and content areas  
3. **Create comprehensive markdown summary** of all content with visual hierarchy
4. **Evaluate current web technologies** and recommend appropriate tech stack for rewrite
5. **Document rationale for technology choices** considering performance, maintainability, and deployment
6. **Set up development environment** for the chosen tech stack
7. **Create basic project structure** and implement core functionality
8. **Test that the walking skeleton works** end-to-end and deploy to staging
9. **Map old content sections** to new structure and implement header/navigation
10. **Implement main content areas**, footer, and additional sections with responsive design
11. **Implement any interactive elements** and test all sections for functionality

### Project Status
- ✅ **All 11 tasks completed successfully**
- ✅ **Website fully functional** at http://localhost:3001
- ✅ **Production build successful** with no errors
- ✅ **GitHub repository synchronized** with all changes
- ✅ **Complete documentation** and project analysis

## Development Workflow

### Repository Structure
This project uses a **submodule architecture** with two separate GitHub repositories:

1. **Main Repository** (`try-cursor-cli`): Documentation, planning, and project management
2. **Website Repository** (`upsoil-soul-nextjs`): Next.js website implementation

### Working with Submodules

#### Initial Setup
```bash
# Clone the main repository with submodules
git clone --recursive https://github.com/MichaelRWolf/try-cursor-cli.git
cd try-cursor-cli

# Or if already cloned, initialize submodules
git submodule update --init --recursive
```

#### Development Workflow

**For Website Changes:**
```bash
# Navigate to the website submodule
cd upsoil-soul-nextjs

# Make changes to website files
# Edit src/components/*.tsx, etc.

# Commit changes in the submodule
git add .
git commit -m "Update website component"
git push origin main

# Update main repository to reference new submodule commit
cd ..
git add upsoil-soul-nextjs
git commit -m "Update website submodule"
git push origin main
```

**For Documentation Changes:**
```bash
# Work in main repository
# Edit README.md, plan.md, etc.

git add .
git commit -m "Update project documentation"
git push origin main
```

#### Syncing Between Environments
```bash
# Pull latest changes from both repositories
git pull origin main
git submodule update --remote

# Push changes to both repositories
git push origin main
cd upsoil-soul-nextjs && git push origin main
```

### Benefits of This Structure
- **Separation of Concerns**: Documentation vs. implementation
- **Independent Development**: Website can be developed separately
- **Version Control**: Each repository maintains its own history
- **Deployment Ready**: Website repository can be deployed independently
- **Collaboration**: Different teams can work on different aspects

