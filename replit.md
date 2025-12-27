# Tamayoze Technical High School Website

## Overview

This is a professional school website for "Tamayoze Technical High School", a Moroccan technical high school. The application is a full-stack web project featuring a React frontend with a modern UI component library and an Express backend with PostgreSQL database storage. The site includes pages for home, announcements, student projects, photo gallery, registration information, and school location.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight React router)
- **State Management**: TanStack React Query for server state
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with custom theme configuration (primary blue #0056b3, secondary green #28a745)
- **Animations**: Framer Motion for page transitions and entry animations
- **Fonts**: DM Sans (body) and Outfit (headings) from Google Fonts

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Server**: HTTP server with Vite dev server integration for development
- **API Design**: RESTful endpoints defined in `shared/routes.ts` with Zod schema validation
- **Database ORM**: Drizzle ORM with PostgreSQL dialect

### Data Storage
- **Database**: PostgreSQL (connection via `DATABASE_URL` environment variable)
- **Schema Location**: `shared/schema.ts` defines three tables:
  - `announcements`: School news with title, date, and content
  - `projects`: Student projects with title, description, and image URL
  - `gallery`: Photo gallery with image URLs and captions
- **Migrations**: Drizzle Kit for database migrations (`drizzle-kit push`)

### Build System
- **Development**: Vite dev server with HMR, tsx for TypeScript execution
- **Production Build**: esbuild for server bundling, Vite for client bundling
- **Output**: `dist/` directory with `public/` for static assets and `index.cjs` for server

### Project Structure
```
client/           # Frontend React application
  src/
    components/   # Reusable UI components
    pages/        # Route page components
    hooks/        # Custom React hooks
    lib/          # Utilities and query client
server/           # Backend Express application
  index.ts        # Server entry point
  routes.ts       # API route definitions
  storage.ts      # Database access layer
  db.ts           # Database connection
shared/           # Shared code between client and server
  schema.ts       # Database schema and types
  routes.ts       # API route definitions with Zod schemas
```

## External Dependencies

### Database
- **PostgreSQL**: Primary database, requires `DATABASE_URL` environment variable
- **Drizzle ORM**: Database toolkit for type-safe queries
- **connect-pg-simple**: PostgreSQL session store (available but not currently used)

### UI Libraries
- **Radix UI**: Full suite of accessible UI primitives (dialog, dropdown, tabs, etc.)
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide React**: Icon library
- **Embla Carousel**: Carousel/slider component
- **Vaul**: Drawer component
- **cmdk**: Command palette component

### Development Tools
- **Vite**: Frontend build tool with React plugin
- **esbuild**: Server-side bundling
- **TypeScript**: Type checking across the codebase
- **Replit plugins**: Runtime error overlay, cartographer, and dev banner for Replit environment