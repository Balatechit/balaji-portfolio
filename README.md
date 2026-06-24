# Balaji V — Portfolio Website
**Next.js 16 · TypeScript · Tailwind CSS**

---

## Quick Start

```bash
npm install
npm run dev      # http://localhost:3000
npm run build    # Production build
```

---

## Folder Structure

```
balaji-portfolio/
├── app/
│   ├── page.tsx          ← Assembles all sections
│   ├── layout.tsx        ← HTML head, fonts, SEO metadata
│   └── globals.css       ← CSS variables, utilities
├── components/
│   ├── Navbar.tsx        ← Sticky nav + CV download button
│   ├── Hero.tsx          ← Landing with particle canvas + 3 CTAs
│   ├── About.tsx         ← Engineering profile
│   ├── FEASection.tsx    ← 25 KL tank — real simulation images
│   ├── CADSection.tsx    ← 8 CAD cards with image carousel
│   ├── Skills.tsx        ← Software bars + skill lists
│   ├── Contact.tsx       ← Email, LinkedIn, CV download
│   └── Footer.tsx
├── lib/
│   └── data.ts           ← ALL content lives here — edit this file
└── public/
    ├── Balaji_V_Resume.pdf   ← YOUR CV (replace this file)
    └── projects/             ← All 26 project images (already included)
        ├── 25kl-tank-stress.jpg
        ├── 25kl-tank-displacement.jpg
        ├── 25kl-tank-mesh.jpg
        ├── 25kl-tank-strain.jpg
        ├── end-wall.jpg
        ├── end-wall-exploded.jpg
        ├── side-wall.jpg
        ├── side-wall-exploded.jpg
        ├── fuel-tank.jpg
        ├── fuel-tank-exploded.jpg
        ├── water-tank.jpg
        ├── water-tank-exploded.jpg
        ├── air-reservoir.jpg
        ├── air-reservoir-2.jpg
        ├── berth-1.jpg  →  berth-10.jpg   (10 images, carousel)
        ├── filter-vessel.jpg
        └── ro-plant.jpg
```

---

## How to Update Your CV

1. Export your updated CV as a PDF
2. Rename it exactly: `Balaji_V_Resume.pdf`
3. Replace the file at `/public/Balaji_V_Resume.pdf`
4. Push to GitHub → Vercel auto-redeploys
5. The download button serves the new file automatically — **no code changes needed**

---

## Deploy to Vercel (Free — ~2 minutes)

### Option A — Deploy from this folder directly (recommended)
```bash
# Inside the balaji-portfolio folder:
git init
git add .
git commit -m "Portfolio v1"
# Create repo on github.com, then:
git remote add origin https://github.com/YOUR_USERNAME/balaji-portfolio.git
git push -u origin main
```
Then: vercel.com → New Project → Import repo → Deploy

Vercel auto-detects Next.js. No root directory setting needed.

### Option B — If you upload the full ZIP
Set Root Directory = `balaji-portfolio` in Vercel project settings.

---

## Update Contact Details

Open `lib/data.ts` — update these two lines:
```ts
email:    "balatecit211@gmail.com",     // already set
linkedin: "https://www.linkedin.com/in/balaji-v211",  // already set
```

---

## Add a New FEA Study

In `lib/data.ts`, push a new object into `feaProjects[]`:
```ts
{
  id: "fea-002",
  title: "Air Reservoir Pressure Study",
  subtitle: "Static Structural FEA — SolidWorks Simulation",
  images: {
    stress: "/projects/air-reservoir-stress.jpg",
    ...
  },
  ...
}
```
Drop the images in `/public/projects/` — the FEA section renders automatically.

---

## Image Carousel (Berth System)

The 3-Tier Berth card shows all 10 images with left/right arrows and dot indicators.
To add more images to any project, add them to the `gallery` array in `data.ts`.

