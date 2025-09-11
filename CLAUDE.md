# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Next.js 14 e-commerce frontend application for VE Studio (vestudio.ca), built with TypeScript and React. The app integrates with Stripe for payments, Builder.io for content management, and Redux Toolkit for state management.

## Tech Stack

- **Framework**: Next.js 14 with App Router
- **Language**: TypeScript
- **State Management**: Redux Toolkit
- **Payment**: Stripe
- **CMS**: Builder.io
- **Styling**: CSS modules
- **Forms**: React Hook Form with Zod validation

## Commands

```bash
# Development
npm run dev

# Build production
npm run build

# Start production server
npm start
```

## Architecture

### Directory Structure

- `/src/app/` - Next.js app router pages and layouts
  - `/checkout/` - Multi-step checkout flow (Contact, Delivery, Payment)
  - `/products/` - Product listing and detail pages
  - `/info/` - Dynamic info pages

- `/src/components/` - React components organized by atomic design
  - `/atoms/` - Basic UI components (Input, Button, Select, etc.)
  - `/organisms/` - Complex components (Header, Footer, Forms)
  - `/layout/` - Layout components and containers

- `/src/lib/` - Core business logic
  - `/redux/store/` - Redux slices (cart, nav, popUp)
  - `/VeProduct/` - Product data handling and API interactions
  - `/stripe/` - Stripe payment utilities
  - `/builderio/` - Builder.io integration

- `/src/types/` - TypeScript type definitions

### State Management

Redux store manages three main slices:
- **cart**: Shopping cart state and operations
- **nav**: Navigation state
- **popUp**: Global popup/modal state

### Key Features

1. **Product Management**: Dynamic product pages with customizable options (color, size, combinations)
2. **Checkout Flow**: Multi-step checkout with address validation and Stripe payment integration
3. **CMS Integration**: Builder.io for dynamic content pages
4. **SEO**: Metadata configuration for all pages

### Environment Variables

Required environment variables (see `.env.example`):
- `NEXT_PUBLIC_VITE_STRIPE_PUBLIC_KEY` - Stripe public key
- `NEXT_PUBLIC_VITE_API_URL` - Backend API URL
- `NEXT_PUBLIC_BUILDER_PUBLIC_KEY` - Builder.io public key

### Path Aliases

TypeScript path alias configured: `@/*` maps to `./src/*`

### ESLint Configuration

ESLint is configured with TypeScript and React Hooks rules. The configuration uses strict TypeScript settings with `noUnusedLocals` and `noUnusedParameters` enabled.