# Graphic Designer Portfolio Template - Customization Guide

This guide will walk you through all the steps needed to personalize this portfolio template with your own information, images, links, and branding.

## Table of Contents

1. [Project Structure](#project-structure)
2. [Personal Information](#personal-information)
3. [Images & Assets](#images--assets)
4. [Navigation & Links](#navigation--links)
5. [Hero Section](#hero-section)
6. [About Section](#about-section)
7. [Projects Section](#projects-section)
8. [Journey/Timeline Section](#journeytimeline-section)
9. [Contact Section](#contact-section)
10. [Colors & Styling](#colors--styling)
11. [Deployment](#deployment)

---

## Project Structure

The main files you'll be editing are located in:
```
client/src/
├── components/
│   ├── layout/
│   │   └── Navbar.tsx           # Navigation bar
│   └── sections/
│       ├── Hero.tsx             # Hero/banner section
│       ├── About.tsx            # About section
│       ├── Projects.tsx         # Portfolio projects
│       ├── Journey.tsx          # Timeline/experience
│       └── Contact.tsx          # Contact & social links
└── assets/                       # Images and media files
```

---

## Personal Information

### 1. **Change Your Name**

#### In the Hero Section
**File:** `client/src/components/sections/Hero.tsx`

Find this code (around line 39):
```tsx
<h1 className="text-5xl md:text-8xl lg:text-9xl font-display font-black tracking-tighter mb-4 leading-none">
  ALEX <span className="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">MORGAN</span>
</h1>
```

Replace `ALEX` and `MORGAN` with your name. The text in the `<span>` tag (currently "MORGAN") will have the gradient effect.

#### In the Navigation Bar
**File:** `client/src/components/layout/Navbar.tsx`

Find this code (around line 33):
```tsx
<a className="text-2xl font-display font-bold tracking-tighter hover:text-primary transition-colors cursor-pointer">
  AM<span className="text-primary">.</span>
</a>
```

Replace `AM` with your initials.

#### In the Footer/About Section
**File:** `client/src/components/sections/Contact.tsx`

Find this code (around line 54):
```tsx
© 2026 ALEX MORGAN. ALL RIGHTS RESERVED.
```

Replace with your name and preferred copyright text.

### 2. **Update Subtitle/Tagline**

**File:** `client/src/components/sections/Hero.tsx`

Find this code (around line 45):
```tsx
<p className="text-lg md:text-2xl text-muted-foreground font-heading max-w-2xl mx-auto mb-10 tracking-wide">
  Crafting immersive digital experiences at the intersection of design and code.
</p>
```

Replace with your own tagline or value proposition.

---

## Images & Assets

### 1. **Replace Hero Background Image**

**File Location:** `client/src/assets/`

The hero background image is referenced in `client/src/components/sections/Hero.tsx` (line 2):
```tsx
import heroBg from "@/assets/hero-bg.png";
```

**To replace:**
1. Create or prepare your background image (recommended: 1920x1080px or larger, PNG/JPG format)
2. Place it in `client/src/assets/` folder
3. Rename it or update the import:
   - If renamed: Update `heroBg` import with your new filename
   - If keeping same name: Simply overwrite the existing `hero-bg.png` file

**What works best:**
- Abstract, atmospheric backgrounds
- Gradients or blurred textures
- High contrast (light or dark, as your design uses opacity)

### 2. **Replace Project Images**

**File:** `client/src/components/sections/Projects.tsx`

Find this code (around line 3):
```tsx
import projectPlaceholder from "@/assets/project-placeholder.png";
```

There are currently 4 project placeholder images being used. You can:

**Option A: Use individual images for each project**
```tsx
import project1 from "@/assets/project-1.png";
import project2 from "@/assets/project-2.png";
import project3 from "@/assets/project-3.png";
import project4 from "@/assets/project-4.png";

const projects = [
  {
    id: 1,
    title: "Neon Finance",
    category: "Fintech Dashboard",
    image: project1,  // Change this
    color: "from-blue-500/20 to-purple-500/20"
  },
  // ... more projects
];
```

**Option B: Keep using placeholder but replace the single image**
- Simply overwrite `project-placeholder.png` with your image

**Image Recommendations:**
- Size: 1200x900px minimum
- Format: PNG or JPG
- Show completed work: Mockups, screenshots, or final designs
- Consistent aspect ratio (4:3 recommended)

### 3. **Upload Assets**

To add new images:
1. Create your image file (or screenshot)
2. Place it in `client/src/assets/`
3. Import it at the top of the component file:
   ```tsx
   import myImage from "@/assets/my-image.png";
   ```
4. Use the imported variable in your component

---

## Navigation & Links

### 1. **Update Navigation Menu**

**File:** `client/src/components/layout/Navbar.tsx`

Find this code (around line 19):
```tsx
const navLinks = [
  { name: "About", href: "#about" },
  { name: "Work", href: "#work" },
  { name: "Journey", href: "#journey" },
  { name: "Contact", href: "#contact" },
];
```

- `name`: The text that appears in the menu
- `href`: The section ID that it links to (uses URL anchors)

**Add or remove links as needed:**
```tsx
const navLinks = [
  { name: "About", href: "#about" },
  { name: "Services", href: "#services" },  // New link
  { name: "Work", href: "#work" },
  { name: "Contact", href: "#contact" },
];
```

### 2. **Update Resume Download Link**

**File:** `client/src/components/layout/Navbar.tsx` and `client/src/components/sections/Contact.tsx`

In Navbar.tsx (around line 45):
```tsx
<Button className="bg-accent text-white hover:bg-accent/90 transition-all font-display px-6 shadow-[0_0_15px_rgba(255,0,212,0.3)] border-none">
  Resume
</Button>
```

Change to:
```tsx
<Button 
  className="bg-accent text-white hover:bg-accent/90 transition-all font-display px-6 shadow-[0_0_15px_rgba(255,0,212,0.3)] border-none"
  onClick={() => window.location.href = '/your-resume.pdf'}
>
  Resume
</Button>
```

Similarly in Contact.tsx:
```tsx
<Button size="lg" variant="outline" className="border-white/20 hover:bg-white/10 font-display px-8 h-14 rounded-full text-lg"
  onClick={() => window.location.href = '/your-resume.pdf'}
>
  Download CV
</Button>
```

Place your resume PDF file in the `client/public/` folder and reference it.

### 3. **Update Email Address**

**File:** `client/src/components/sections/Contact.tsx`

Find this code (around line 40):
```tsx
onClick={() => window.location.href = 'mailto:alex@example.com?subject=Project Inquiry'}
```

Replace `alex@example.com` with your email address.

### 4. **Update Social Media Links**

**File:** `client/src/components/sections/Contact.tsx`

Find this code (around line 48):
```tsx
const socials = [
  { icon: Dribbble, href: "https://dribbble.com" },
  { icon: Twitter, href: "https://twitter.com" },
  { icon: Linkedin, href: "https://linkedin.com" }
];
```

Replace with your actual social media URLs:
```tsx
const socials = [
  { icon: Dribbble, href: "https://dribbble.com/yourhandle" },
  { icon: Twitter, href: "https://twitter.com/yourhandle" },
  { icon: Linkedin, href: "https://linkedin.com/in/yourprofile" }
];
```

**To add more social links:**
- Import additional icons from `lucide-react`:
  ```tsx
  import { Dribbble, Twitter, Linkedin, Github, Instagram } from "lucide-react";
  ```
- Add them to the socials array:
  ```tsx
  const socials = [
    { icon: Dribbble, href: "https://dribbble.com/yourhandle" },
    { icon: Twitter, href: "https://twitter.com/yourhandle" },
    { icon: Linkedin, href: "https://linkedin.com/in/yourprofile" },
    { icon: Github, href: "https://github.com/yourprofile" },
    { icon: Instagram, href: "https://instagram.com/yourprofile" }
  ];
  ```

---

## Hero Section

**File:** `client/src/components/sections/Hero.tsx`

### Change the Badge Text
Find this code (around line 34):
```tsx
<span className="inline-block py-1.5 px-4 rounded-full border border-primary/30 bg-primary/20 backdrop-blur-md text-xs font-bold tracking-[0.2em] uppercase text-white mb-6 neon-box">
  Portfolio 2026
</span>
```

Replace `Portfolio 2026` with your preferred text (e.g., `Available for Hire`, `Product Designer`, etc.)

### Adjust the Background Parallax
The opacity animation can be tweaked in the Hero component. To change the starting/ending opacity:
```tsx
const opacity = useTransform(scrollY, [0, 300], [1, 0]);  // Adjust these numbers
```

---

## About Section

**File:** `client/src/components/sections/About.tsx`

### 1. **Update Your Bio**

Find this code (around line 24):
```tsx
<h2 className="text-4xl md:text-5xl font-display font-bold mb-8">
  Behind the <span className="text-accent">Pixel</span>
</h2>
<div className="space-y-6 text-lg text-muted-foreground font-heading">
  <p>
    I am a multidisciplinary designer based in Neo-Tokyo, obsessed with the details that bridge the gap between human intuition and machine logic.
  </p>
  <p>
    With over 5 years of experience in digital product design, I focus on creating interfaces that aren't just usable, but memorable. I believe that good design dissolves into behavior.
  </p>
</div>
```

Replace:
- The text in the heading (`Behind the Pixel`)
- Both paragraphs with your own biography
- Update your location (currently "Neo-Tokyo")
- Update your years of experience

### 2. **Update Skills List**

Find this code (around line 36):
```tsx
const skills = [
  "Product Design", "UI/UX", "Interaction Design", 
  "Framer Motion", "React", "WebGL", "3D Modeling"
];
```

Replace with your actual skills. Add or remove as needed:
```tsx
const skills = [
  "Your Skills", "Here", "Updated", 
  "List", "Removed", "Old", "Skills"
];
```

### 3. **Update Terminal Output**

The terminal display shows custom text around line 63:
```tsx
<div className="font-mono text-sm space-y-4">
  <div>
    <span className="text-primary">➜</span> <span className="text-blue-400">~</span> whoami
  </div>
  <div className="text-muted-foreground pl-4">
    "Alex Morgan"<br/>
    "Design Engineer"<br/>
    "Visual Storyteller"
  </div>
  
  <div>
    <span className="text-primary">➜</span> <span className="text-blue-400">~</span> locate
  </div>
  <div className="text-muted-foreground pl-4">
    "San Francisco, CA"
  </div>
  
  <div>
    <span className="text-primary">➜</span> <span className="text-blue-400">~</span> status
  </div>
  <div className="text-green-400 pl-4">
    ● Open to Work
  </div>
</div>
```

Update:
- `"Alex Morgan"` with your name
- The role descriptions (Design Engineer, Visual Storyteller)
- Your location (San Francisco, CA)
- Availability status (Open to Work / Freelance / Not Accepting)

---

## Projects Section

**File:** `client/src/components/sections/Projects.tsx`

### Update Project Data

Find this code (around line 4):
```tsx
const projects = [
  {
    id: 1,
    title: "Neon Finance",
    category: "Fintech Dashboard",
    image: projectPlaceholder,
    color: "from-blue-500/20 to-purple-500/20"
  },
  {
    id: 2,
    title: "Aether OS",
    category: "Spatial Interface",
    image: projectPlaceholder,
    color: "from-pink-500/20 to-rose-500/20"
  },
  // ... more projects
];
```

### To customize each project:

**Add a new project:**
```tsx
const projects = [
  // ... existing projects
  {
    id: 5,
    title: "Your Project Name",
    category: "Your Category",
    image: yourImage,  // Import at top: import yourImage from "@/assets/..."
    color: "from-teal-500/20 to-cyan-500/20"  // Choose your gradient colors
  }
];
```

**Color options for gradients:**
- Blue: `from-blue-500/20 to-purple-500/20`
- Pink: `from-pink-500/20 to-rose-500/20`
- Green: `from-emerald-500/20 to-teal-500/20`
- Orange: `from-orange-500/20 to-red-500/20`
- Cyan: `from-cyan-500/20 to-blue-500/20`
- Purple: `from-purple-500/20 to-pink-500/20`

### Add Project Links

Currently, projects don't navigate anywhere. To make them clickable:

1. Add a `link` property to each project:
```tsx
{
  id: 1,
  title: "Neon Finance",
  category: "Fintech Dashboard",
  image: projectPlaceholder,
  color: "from-blue-500/20 to-purple-500/20",
  link: "https://yourproject.com"  // Add this
}
```

2. Update the rendering to make it clickable:
```tsx
<motion.div
  key={project.id}
  onClick={() => project.link && window.open(project.link, '_blank')}
  // ... rest of the code
>
```

### Remove or Add Projects

To show fewer projects, simply remove items from the array. To add more, follow the pattern above.

---

## Journey/Timeline Section

**File:** `client/src/components/sections/Journey.tsx`

### Update Timeline Events

Find this code (around line 3):
```tsx
const events = [
  {
    year: "2026",
    title: "The Future",
    subtitle: "AI & Design Synthesis",
    desc: "Exploring the boundaries of generative interfaces and predictive UX paradigms.",
    side: "left"
  },
  {
    year: "2024",
    title: "Metaverse Lab",
    subtitle: "Lead Product Designer",
    desc: "Architecting design systems for spatial computing and immersive 3D environments.",
    side: "right"
  },
  // ... more events
];
```

**To update each event:**
- `year`: The year (e.g., "2023", "2022", etc.)
- `title`: Main heading (e.g., company name, milestone)
- `subtitle`: Role or secondary heading
- `desc`: Full description of the experience
- `side`: `"left"` or `"right"` for alternating layout

**Example of updating:**
```tsx
const events = [
  {
    year: "2024",
    title: "Current Company",
    subtitle: "Lead Designer",
    desc: "Leading design initiatives and mentoring junior designers.",
    side: "left"
  },
  {
    year: "2022",
    title: "Previous Company",
    subtitle: "Senior UX Designer",
    desc: "Designed and shipped 5+ major product features.",
    side: "right"
  },
];
```

### Add or Remove Timeline Events

Simply add more objects to the array or remove existing ones. The component automatically handles the layout alternation.

---

## Contact Section

**File:** `client/src/components/sections/Contact.tsx`

### Update Contact Heading

Find this code (around line 26):
```tsx
<h2 className="text-5xl md:text-7xl font-display font-black mb-8 leading-tight">
  LET'S BUILD THE <br />
  <span className="text-transparent bg-clip-text bg-gradient-to-r from-secondary to-accent">FUTURE</span>
</h2>
```

Update the text and keep the gradient span if desired, or remove it:
```tsx
<h2 className="text-5xl md:text-7xl font-display font-black mb-8 leading-tight">
  LET'S <span className="text-transparent bg-clip-text bg-gradient-to-r from-secondary to-accent">WORK TOGETHER</span>
</h2>
```

### Update Contact Description

Find this code (around line 33):
```tsx
<p className="text-xl text-muted-foreground mb-12 font-heading leading-relaxed">
  I'm currently available for freelance projects and open to full-time opportunities. 
  If you have an idea that challenges the status quo, I'd love to hear it.
</p>
```

Update with your current situation and availability.

### Customize Email Subject

The email button currently has:
```tsx
onClick={() => window.location.href = 'mailto:alex@example.com?subject=Project Inquiry'}
```

Change the subject line:
```tsx
onClick={() => window.location.href = 'mailto:your@email.com?subject=Let\'s Collaborate'}
```

---

## Colors & Styling

### 1. **Primary Colors**

Colors are defined using CSS variables. The main colors used are:
- **primary**: The accent/highlight color (currently magenta/pink)
- **secondary**: Secondary accent color
- **accent**: Bright accent (neon pink)
- **background**: Main background color
- **foreground**: Text color

### 2. **Change Theme Colors (If CSS is available)**

Look for `tailwind.config.js` or `globals.css` files. The colors can be adjusted by modifying:
- CSS custom properties (`--primary`, `--secondary`, etc.)
- Tailwind configuration

### 3. **Color Classes Used**

Common color classes you'll see:
- `text-primary` - Primary color text
- `bg-primary` - Primary color background
- `border-primary` - Primary color border
- `text-accent` - Bright accent text
- `bg-accent` - Bright accent background

### 4. **Modify Specific Element Colors**

To change a button color:
```tsx
{/* Change this: */}
<Button className="bg-accent text-white hover:bg-accent/90">Button</Button>

{/* To: */}
<Button className="bg-blue-600 text-white hover:bg-blue-700">Button</Button>
```

---

## Before You Deploy

### Checklist

- [ ] Changed your name in Hero section
- [ ] Updated your bio in About section
- [ ] Changed all placeholder images
- [ ] Updated your email address in Contact section
- [ ] Updated social media links
- [ ] Updated projects with real work
- [ ] Updated timeline/journey section
- [ ] Changed navigation links if needed
- [ ] Updated footer copyright year and name
- [ ] Tested all links work correctly
- [ ] Checked mobile responsiveness
- [ ] Reviewed all text for typos and accuracy

## Deployment

### Building for Production

```bash
npm run build
```

### Preview Before Publishing

```bash
npm run preview
```

### Running Locally for Development

```bash
npm run dev
```

The site will be available at `http://localhost:5000`

---

## File Location Quick Reference

| Change | File |
|--------|------|
| Your Name | `Hero.tsx`, `Navbar.tsx`, `Contact.tsx` |
| Bio/About | `About.tsx` |
| Skills | `About.tsx` |
| Projects | `Projects.tsx` |
| Timeline/Journey | `Journey.tsx` |
| Email | `Contact.tsx` |
| Social Links | `Contact.tsx` |
| Images | `client/src/assets/` |
| Resume Link | `Navbar.tsx`, `Contact.tsx` |
| Navigation Menu | `Navbar.tsx` |
| Resume File | `client/public/` |

---

## Tips for Best Results

1. **Images**: Use high-quality images. Resize them appropriately before adding (1200x900px for projects is ideal)
2. **Text**: Keep descriptions concise but impactful
3. **Links**: Always test external links work correctly
4. **Colors**: Stick with the existing color scheme for cohesion, or update all sections consistently
5. **Mobile**: The template is responsive - test on mobile devices
6. **Performance**: Optimize images to reduce file size and loading time

---

## Troubleshooting

**Images not showing?**
- Check the import path in the component
- Ensure the image file is in `client/src/assets/`
- Verify the filename spelling matches exactly

**Links not working?**
- Make sure URLs include `https://`
- Test the link in a browser first
- Check for typos

**Colors not changing?**
- Clear browser cache (Ctrl+Shift+Delete)
- Restart the development server
- Check for typos in class names

**Import errors?**
- Ensure the file exists in the specified location
- Check import path uses `@/assets/` for files in src/assets folder

---

**Happy customizing! Your portfolio is now ready to showcase your work!**
