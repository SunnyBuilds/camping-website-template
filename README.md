# Wild Nature Journey

A modern camping gear review and affiliate marketing website built with Next.js 16, featuring product reviews, buying guides, and Amazon affiliate integration.

## 🎯 Project Overview

Wild Nature Journey is a static camping gear review site that helps outdoor enthusiasts find the best equipment. The site features:

- 30+ curated camping products across 4 categories
- Detailed product reviews with pros/cons analysis
- In-depth buying guides and articles
- Amazon Associates affiliate integration
- SEO-optimized content with structured data
- Mobile-responsive design

## 🛠️ Technology Stack

### Core Framework
- **Next.js 16.0.10** - React framework with App Router
- **React 19.2.0** - UI library
- **TypeScript 5** - Type-safe development (strict mode)

### Styling & UI
- **Tailwind CSS 4.1.9** - Utility-first CSS framework (CSS-first configuration)
- **shadcn/ui** - Component library built on Radix UI primitives
- **Lucide React** - Icon library

### Content & SEO
- **MDX** - Markdown with JSX for rich content
- **next-mdx-remote** - Server-side MDX rendering
- **JSON-LD** - Structured data for search engines

### Development Tools
- **ESLint** - Code linting
- **PostCSS** - CSS processing
- **TypeScript** - Static type checking

## 📁 Project Structure

```
camping-website-template/
├── app/                          # Next.js App Router pages
│   ├── page.tsx                  # Homepage
│   ├── product/[asin]/          # Dynamic product pages
│   ├── review/[slug]/           # MDX review articles
│   ├── category/[category]/     # Category listing pages
│   ├── about/                   # About page
│   ├── contact/                 # Contact page
│   └── layout.tsx               # Root layout
├── components/                   # React components
│   ├── ui/                      # shadcn/ui components
│   ├── amazon-button.tsx        # Affiliate CTA button
│   ├── affiliate-disclosure.tsx # FTC compliance disclosure
│   ├── pros-cons.tsx            # Product pros/cons display
│   ├── header.tsx               # Site header
│   └── footer.tsx               # Site footer
├── lib/                         # Utilities and data
│   ├── products-data.ts         # Product catalog (30 products)
│   └── utils.ts                 # Helper functions
├── content/                     # MDX content files
│   └── reviews/                 # Review articles
├── public/                      # Static assets
│   └── images/                  # Product images
└── next.config.mjs              # Next.js configuration
```

## 🎨 Key Features

### Product Catalog
- **30 Products** across 4 categories:
  - Tents (8 products)
  - Sleeping Bags (8 products)
  - Backpacks (7 products)
  - Camping Stoves (7 products)

### Product Data Structure
```typescript
interface Product {
  asin: string          // Amazon ASIN
  title: string         // Full product name
  brand: string         // Manufacturer
  features: string[]    // Key features
  amazonUrl: string     // Affiliate link
  imageUrl: string      // Product image
  rating?: number       // Star rating
  category: string      // Product category
  shortTitle?: string   // Display name
  summary?: string      // Brief description
  slug?: string         // URL slug
}
```

### Amazon Affiliate Components
- **AmazonButton**: Styled CTA with `rel="nofollow sponsored"` and `target="_blank"`
- **AffiliateDisclosure**: FTC-compliant disclosure notice
- **ProsCons**: Two-column pros/cons comparison display

### SEO Optimization
- Dynamic metadata generation for all pages
- JSON-LD structured data (Product, Review, BreadcrumbList)
- Semantic HTML with proper heading hierarchy
- Open Graph and Twitter Card meta tags
- Sitemap generation

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

```bash
# Install dependencies
npm install

# Run development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the site.

### Available Scripts

```bash
npm run dev      # Start development server
npm run build    # Build for production (static export)
npm run start    # Start production server
npm run lint     # Run ESLint
```

## 📦 Build & Deployment

The project is configured for **static export** (JAMstack):

```javascript
// next.config.mjs
export default {
  output: 'export',
  images: { unoptimized: true }
}
```

### Build Output
```bash
npm run build
```

Generates static files in the `out/` directory, ready for deployment to:
- Netlify
- Vercel
- GitHub Pages
- AWS S3 + CloudFront
- Any static hosting service

## 🎯 Page Routes

The site includes 15+ routes:

### Static Pages
- `/` - Homepage with hero, categories, featured products
- `/about` - About page
- `/contact` - Contact page
- `/guides/tent-buying-guide` - Tent buying guide
- `/guides/sleeping-bag-guide` - Sleeping bag guide
- `/guides/backpack-guide` - Backpack guide

### Dynamic Pages
- `/product/[asin]` - Individual product pages (30 products)
- `/category/[category]` - Category listing pages (4 categories)
- `/review/[slug]` - MDX review articles

## 🎨 Design System

### Tailwind CSS 4 Configuration
- CSS-first configuration in `app/globals.css`
- Custom color palette with CSS variables
- Dark mode support via `class` strategy
- Responsive breakpoints: sm, md, lg, xl, 2xl

### Component Library
- Built with **shadcn/ui** pattern
- Radix UI primitives for accessibility
- Customizable via `components.json`
- Components in `components/ui/`

## 📝 Content Management

### MDX Reviews
Review articles are stored in `content/reviews/` as MDX files with frontmatter:

```mdx
---
title: "Product Review Title"
description: "SEO description"
date: "2024-01-15"
author: "Author Name"
category: "tents"
---

# Review Content

Your MDX content with React components...
```

### Adding New Products
Edit `lib/products-data.ts` to add products to the catalog:

```typescript
export const products: Product[] = [
  {
    asin: "B0XXXXXX",
    title: "Product Name",
    brand: "Brand Name",
    category: "tents",
    features: ["Feature 1", "Feature 2"],
    amazonUrl: "https://amazon.com/...",
    imageUrl: "/images/product.jpg",
    rating: 4.5
  }
]
```

## 🔗 Amazon Associates Integration

### Affiliate Links
All Amazon links include:
- Your Amazon Associates tracking ID
- `rel="nofollow sponsored"` attributes
- `target="_blank"` for external navigation

### Compliance
- FTC-compliant disclosure on all pages
- Clear affiliate relationship statements
- Proper link attribution

## 📊 SEO Features

- **Metadata**: Dynamic title, description, keywords for each page
- **Structured Data**: JSON-LD for products, reviews, breadcrumbs
- **Semantic HTML**: Proper heading hierarchy, landmarks
- **Image Optimization**: Alt text, lazy loading
- **Performance**: Static generation, optimized assets

## 🤝 Contributing

This is a template project. Feel free to:
- Customize the design and branding
- Add more products and categories
- Create additional review articles
- Modify the component library
- Enhance SEO and performance

## 📄 License

This project is open source and available for personal and commercial use.

## 🔧 Configuration Files

- `next.config.mjs` - Next.js configuration (static export)
- `tailwind.config.ts` - Tailwind CSS configuration
- `tsconfig.json` - TypeScript configuration (strict mode)
- `postcss.config.mjs` - PostCSS with Tailwind CSS 4
- `components.json` - shadcn/ui configuration

## 📞 Support

For questions or issues with this template, please refer to the official documentation:
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com)

---

Built with ❤️ for outdoor enthusiasts
