# Arrivo Stay Discovery App

A production-quality short stay discovery application built with Next.js 14, React, and Tailwind CSS.
Designed for the Arrivo Frontend Engineer Assessment.

## Features

- **Stay Discovery**: Browse short stay listings with advanced filtering.
- **Responsive Design**: Mobile-first approach using Tailwind CSS.
- **Performance Optimized**:
  - Server Components for initial load and SEO.
  - `next/image` for optimized image delivery.
  - Client components only where interactivity is required.
- **Search & Filter**: Filter by location, dates, guests, and price.
- **Interactive UI**: Custom dropdowns, swipers, and animated transitions.

## Tech Stack

- **Framework**: [Next.js 14](https://nextjs.org/) (App Router)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Icons**: Custom SVG icons & Lucide React
- **Animation**: CSS Transitions
- **Deployment**: Vercel

## Rendering Strategy

We utilize **Next.js Server Components** as the default to ensure minimal JavaScript bundle size and maximum SEO performance.

- **Server Components**: Used for all layout wrappers, static content pages (Home, About, Services), and initial data fetching.
- **Client Components**: Used specifically for interactive elements such as:
  - `PropertiesHero` (Search/Filter state)
  - `MobileMenu` (Navigation state)
  - `Testimonials` & `FeaturedProperties` (Swiper interactions)
  - `LetsMakeItHappen` (Form handling)

This hybrid approach ensures excellent **Core Web Vitals** (LCP, CLS) while maintaining a rich user experience.

### Dynamic Routing & Data Fetching

- **Property Details (`/properties/[id]`)**:
  - Uses `generateStaticParams` to statically generate routes for all properties at build time (SSG), ensuring instant page loads.
  - Implements `dynamicParams = true` to allow on-demand generation for new properties.
  - Data is fetched from a centralized mock source (`data/properties.ts`) simulating an API response.
- **Loading States**:
  - `loading.tsx` is implemented for the detail page to show a skeleton loader during navigation, enhancing perceived performance.

## Setup Instructions

1. **Clone the repository**:

   ```bash
   git clone <repository-url>
   cd real-estate
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Run development server**:

   ```bash
   npm run dev
   ```

4. **Build for production**:
   ```bash
   npm run build
   npm start
   ```

## SEO & Performance Checklist

- [x] **Semantic HTML**: Proper use of `<section>`, `<h1>`, `<nav>`, and landmark roles.
- [x] **Metadata**: Dynamic title and description for listing pages (`generateMetadata`).
- [x] **Structured Data**: JSON-LD (`Accommodation` schema) implemented on property detail pages.
- [x] **Image Optimization**: `next/image` used for automatic resizing, format conversion (WebP/AVIF), and lazy loading.
- [x] **Core Web Vitals**: Optimized for LCP (Server Components), CLS (Image sizing), and INP (minimal JS).
- [x] **Accessibility**: ARIA labels on buttons, keyboard navigable interactive elements, and sufficient color contrast.
- [x] **Responsive Design**: Mobile-first architecture using Tailwind CSS breakpoints.

## Project Structure

- `/app`: App Router pages and layouts.
- `/components`: Reusable UI components (grouped by feature/page).
- `/public`: Static assets (images, icons).
- `/styles`: Global styles and Tailwind configuration.

## Screenshots

![Screenshot 1](public/screenshots/screenshot-01.png)
![Screenshot 2](public/screenshots/screenshot-02.png)
![Screenshot 3](public/screenshots/screenshot-03.png)
![Screenshot 4](public/screenshots/screenshot-04.png)
![Screenshot 5](public/screenshots/screenshot-05.png)
![Screenshot 6](public/screenshots/screenshot-06.png)
![Screenshot 7](public/screenshots/screenshot-07.png)
