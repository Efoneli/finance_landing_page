# Finance Landing Page - Staco

A modern, animated finance landing page built with Nuxt 4, featuring motion tabs navigation, text rotation animations, and beautiful UI components.

## 🚀 Live Demo
[Add your deployed URL here]

## 📋 Features

### ✨ Implemented Features

1. **Animated Motion Tabs Navigation**
   - Smooth sliding background indicator
   - Pills-style navigation
   - Responsive design
   - Active state animations

2. **Hero Section with Text Rotation**
   - Rotating words: "Easier", "Accountable", "Reliable", "Secure", "Simple"
   - Smooth text transitions
   - Video player with play/pause controls
   - Decorative background elements (circles and curved lines)

3. **Features Section**
   - 6 feature cards with icons
   - Scroll-triggered animations
   - Hover effects

4. **Testimonials Section**
   - Customer reviews with ratings
   - Animated on scroll
   - Avatar placeholders

5. **Pricing Section**
   - 3 pricing tiers
   - Highlighted "Most Popular" plan
   - Feature lists with checkmarks

6. **CTA Section**
   - Gradient background
   - Call-to-action buttons
   - Decorative overlays

7. **Footer**
   - Multi-column layout
   - Social media links
   - Company information

### 🎨 Design Features

- **Dark theme hero section** with navy background (#1a1f2e)
- **Emerald green accents** (#10b981 / emerald-500)
- **Smooth animations** using @vueuse/motion
- **Responsive design** for all screen sizes
- **Modern UI components** with TailwindCSS

## 🛠️ Tech Stack

- **Nuxt 4** - Vue.js framework
- **TypeScript** - Type safety
- **TailwindCSS** - Utility-first CSS
- **@vueuse/motion** - Vue animation library
- **HTML5 Video** - Video player

## 📦 Installation

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

Visit `http://localhost:3000` to view the app.

## 🏗️ Project Structure

```
finance-landing-page/
├── components/
│   ├── MotionTabs.vue          # Animated navigation tabs
│   ├── HeroSection.vue         # Hero with text rotation & video
│   ├── FeaturesSection.vue     # Features grid
│   ├── TestimonialsSection.vue # Customer testimonials
│   ├── PricingSection.vue      # Pricing cards
│   ├── CTASection.vue          # Call to action
│   └── Footer.vue              # Footer with links
├── pages/
│   └── index.vue               # Main landing page
├── public/
│   └── videos/                 # Video assets
├── app.vue                     # Root component
├── nuxt.config.ts              # Nuxt configuration
├── package.json                # Dependencies
└── README.md                   # This file
```

## 🎯 Key Implementation Details

### 1. Motion Tabs Navigation

**Animation Type:** Sliding background indicator  
**Implementation:**
- Uses Vue refs to track active tab
- Dynamically calculates position and width
- CSS transitions for smooth movement
- Fixed positioning at top of page

**Code Location:** `components/MotionTabs.vue`

```javascript
const updateIndicator = () => {
  if (tabRefs.value[activeTab.value]) {
    const activeElement = tabRefs.value[activeTab.value]
    indicatorLeft.value = activeElement.offsetLeft
    indicatorWidth.value = activeElement.offsetWidth
  }
}
```

### 2. Text Rotation Animation

**Animation Type:** Word cycling with fade effect  
**Implementation:**
- Array of words to cycle through
- setInterval to change word every 2.5 seconds
- Smooth CSS transitions

**Code Location:** `components/HeroSection.vue`

```javascript
const words = ['Easier', 'Accountable', 'Reliable', 'Secure', 'Simple']

onMounted(() => {
  setInterval(() => {
    currentIndex.value = (currentIndex.value + 1) % words.length
    currentWord.value = words[currentIndex.value]
  }, 2500)
})
```

### 3. Video Player

**Implementation:**
- HTML5 `<video>` element
- Autoplay, loop, muted for autoplay to work
- Custom play/pause button overlay
- Uses free stock video from Mixkit

**Video Source:** You can replace with your own video by updating the `videoSrc` variable

### 4. Scroll Animations

**Library:** `@vueuse/motion`  
**Implementation:**
- `v-motion` directive on components
- Initial state (hidden, offset)
- Visible state (shown, normal position)
- Staggered delays for sequential appearance

**Example:**
```vue
<div 
  v-motion
  :initial="{ opacity: 0, y: 50 }"
  :visible="{ opacity: 1, y: 0, transition: { delay: 100 } }"
>
  Content
</div>
```

### 5. Decorative Elements

**Background Circles:**
- Absolute positioned divs
- Blur filters for glow effect
- Low opacity emerald colors

**Curved Lines:**
- SVG paths with quadratic curves
- Positioned absolutely
- Decorative only, no interaction

## 🎨 Color Palette

```css
Primary Background: #1a1f2e (dark navy)
Primary Accent: #10b981 (emerald-500)
Secondary Accent: #34d399 (emerald-400)
Text Dark: #111827 (gray-900)
Text Light: #ffffff (white)
Text Muted: #9ca3af (gray-400)
```

## 📐 Sections Breakdown

### Hero Section (HeroSection.vue)
- **Purpose:** First impression, main value proposition
- **Elements:** 
  - Animated headline with rotating words
  - Subheading
  - CTA buttons
  - Video showcase
- **Animations:** Text rotation, decorative shapes

### Features Section (FeaturesSection.vue)
- **Purpose:** Showcase platform capabilities
- **Elements:** 6 feature cards with icons
- **Animations:** Scroll-triggered fade-in with stagger

### Testimonials Section (TestimonialsSection.vue)
- **Purpose:** Social proof, build trust
- **Elements:** 3 customer testimonials with ratings
- **Animations:** Scale-in on scroll

### Pricing Section (PricingSection.vue)
- **Purpose:** Convert visitors to customers
- **Elements:** 3 pricing tiers (Starter, Professional, Enterprise)
- **Animations:** Slide-up on scroll
- **Special:** Middle tier highlighted and scaled

### CTA Section (CTASection.vue)
- **Purpose:** Final conversion push
- **Elements:** Large headline, description, CTA buttons
- **Background:** Gradient with decorative blurs

### Footer (Footer.vue)
- **Purpose:** Additional navigation, legal info
- **Elements:** 
  - Logo and description
  - Social media links
  - Link columns (Product, Company, Resources)
  - Copyright and contact

## 🎬 Video Resources

The hero section uses a video player. You have several options:

### Option 1: Use Stock Video (Current)
Currently uses: Mixkit business video
- Free to use
- No attribution required
- URL: https://assets.mixkit.co/videos/...

### Option 2: Use Your Own Video
Replace the `videoSrc` variable in `HeroSection.vue`:
```javascript
const videoSrc = '/videos/your-video.mp4'
```
Place your video in: `public/videos/your-video.mp4`

### Option 3: Free Stock Video Sites
- **Pexels Videos:** https://www.pexels.com/videos/
- **Pixabay:** https://pixabay.com/videos/
- **Mixkit:** https://mixkit.co/free-stock-video/

**Recommended search terms:**
- "business meeting"
- "office collaboration"
- "team working"
- "financial planning"

### Video Requirements
- Format: MP4 (H.264)
- Recommended size: 1920x1080 or 1280x720
- Keep file size under 10MB for fast loading
- Optimize using tools like HandBrake

## 🚀 Deployment

### Deploy to Vercel (Recommended)

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

### Deploy to Netlify

```bash
# Build
npm run generate

# Drag & drop the .output/public folder to Netlify
```

### Environment Variables
No environment variables needed for this project.

## 📊 Performance Optimization

### Current Optimizations
1. ✅ Lazy loading for images
2. ✅ Minimal JavaScript bundle
3. ✅ TailwindCSS purging (automatic)
4. ✅ Component-based architecture

### Future Optimizations
- [ ] Add image optimization with Nuxt Image
- [ ] Implement lazy loading for video
- [ ] Add service worker for caching
- [ ] Optimize font loading

## 🎨 Customization Guide

### Change Colors
Edit TailwindCSS classes:
- Green/Emerald → Replace `emerald-` with `blue-`, `purple-`, etc.
- Dark background → Change `#1a1f2e` in HeroSection

### Change Text
- Hero headline: Edit in `HeroSection.vue`
- Rotating words: Modify `words` array in `HeroSection.vue`
- Features: Edit content in `FeaturesSection.vue`

### Add/Remove Sections
Edit `pages/index.vue`:
```vue
<template>
  <div>
    <MotionTabs />
    <HeroSection />
    <!-- Add your custom section here -->
    <YourCustomSection />
  </div>
</template>
```

## 📝 Notes for Assessors

### Sections Omitted (As Requested)
- ✅ Blog posts section - Skipped
- ✅ Stats/metrics section - Skipped  
- ✅ Detailed features/benefits section - Skipped

### Animations Implemented
- ✅ Motion tabs navigation with sliding indicator
- ✅ Text rotation in hero headline
- ✅ Scroll-triggered animations throughout
- ✅ Hover effects on buttons and cards
- ✅ Video player controls

### Responsive Design
- ✅ Mobile: Single column layouts
- ✅ Tablet: 2-column layouts
- ✅ Desktop: 3+ column layouts
- ✅ Navigation adapts to screen size

### Lighthouse Scores (Expected)
- Performance: 90+
- Accessibility: 95+
- Best Practices: 95+
- SEO: 100

## 🐛 Known Issues & Solutions

**Issue:** Video doesn't autoplay on mobile  
**Solution:** Videos must be muted for autoplay to work. Current implementation handles this.

**Issue:** Motion tabs jump on page load  
**Solution:** Indicator position calculated `onMounted()`. Small delay is normal.

**Issue:** Text rotation appears jumpy  
**Solution:** CSS transition smooths changes. Adjust timing in HeroSection.vue if needed.

## 🤝 Contributing

This is an assessment project, but suggestions welcome:
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

MIT License - Feel free to use for learning purposes

## 👨‍💻 Developer

Abba Efoneli Sarah

## 📧 Contact

For questions about this implementation:
- Email: efonelisarah@gmail.com
- GitHub: github.com/efoneli

---

**Built with ❤️ using Nuxt 4, Vue 3, and TailwindCSS**