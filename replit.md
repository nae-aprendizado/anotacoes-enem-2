# NAE Anotações - Notes Management System

## Overview

NAE Anotações is a full-stack web application for managing educational notes with Google Drive integration. The system allows users to create, organize, and access their notes through automatically generated Google Docs, providing a seamless note-taking experience for students.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management
- **UI Framework**: Radix UI components with shadcn/ui styling
- **Styling**: Tailwind CSS with custom design system
- **Build Tool**: Vite with custom configuration for development and production

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js for REST API
- **Database**: PostgreSQL with Drizzle ORM
- **Session Management**: Express sessions with PostgreSQL store
- **External Integration**: Google Drive and Google Docs APIs

### Database Architecture
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Migration Strategy**: Schema-based migrations in TypeScript
- **Connection**: Neon serverless PostgreSQL with connection pooling

## Key Components

### Authentication System
- **Session-based Authentication**: Uses express-session with PostgreSQL storage
- **User Management**: Simple email-based user registration and login
- **Middleware**: Custom authentication middleware for protected routes

### Note Management
- **CRUD Operations**: Full create, read, update, delete functionality for notes
- **Subject Organization**: Predefined subject categories for note classification
- **Search & Filter**: Text-based search and subject-based filtering
- **Statistics**: Dashboard analytics for user note activity

### Google Drive Integration
- **Service Account Authentication**: JWT-based authentication with Google APIs
- **Document Creation**: Automatic Google Docs creation for each note
- **Permission Management**: Automatic sharing of documents with users
- **External Access**: Direct links to Google Docs for note editing

### UI Components
- **Design System**: Custom purple-pink gradient theme with neutral base colors
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Component Library**: Comprehensive set of Radix UI components
- **Toast Notifications**: User feedback system for actions and errors

## Data Flow

1. **User Authentication**: Email-based login creates or retrieves user session
2. **Note Creation**: User creates note → Google Doc generated → Note record saved to database
3. **Note Access**: Dashboard displays user notes with search/filter capabilities
4. **Note Editing**: Users can edit note titles in-app or access Google Docs directly
5. **Statistics**: Real-time calculation of user activity metrics

## External Dependencies

### Core Dependencies
- **Database**: @neondatabase/serverless for PostgreSQL connection
- **ORM**: drizzle-orm and drizzle-kit for database operations
- **Google APIs**: googleapis for Drive and Docs integration
- **UI Framework**: Multiple @radix-ui packages for component primitives
- **State Management**: @tanstack/react-query for server state
- **Validation**: zod with drizzle-zod for schema validation

### Development Tools
- **Build**: Vite with React plugin and custom configuration
- **TypeScript**: Full type safety across frontend and backend
- **CSS**: Tailwind CSS with PostCSS processing
- **Development**: tsx for TypeScript execution and hot reloading

### Environment Variables Required
- `DATABASE_URL`: PostgreSQL connection string
- `GOOGLE_CLIENT_EMAIL`: Service account email
- `GOOGLE_PRIVATE_KEY`: Service account private key

## Deployment Strategy

### Build Process
- **Frontend**: Vite builds React app to dist/public
- **Backend**: esbuild bundles server code to dist/index.js
- **Static Assets**: Frontend assets served by Express in production

### Production Configuration
- **Server**: Express serves both API and static frontend
- **Database**: PostgreSQL with connection pooling for scalability
- **Sessions**: Persistent session storage in PostgreSQL
- **Error Handling**: Comprehensive error middleware with logging

### Development Environment
- **Hot Reloading**: Vite development server with HMR
- **Database**: Local or cloud PostgreSQL instance
- **API Proxy**: Vite proxies API requests to Express server
- **TypeScript**: Incremental compilation with strict type checking

## Changelog

Changelog:
- June 24, 2025: Sistema NAE Anotações implementado com sucesso
  - Sistema de login por email funcionando
  - Interface roxo/rosa implementada conforme design
  - 15 matérias com cores específicas adicionadas
  - Integração Google Drive configurada (com fallback para criação de documentos)
  - Dashboard com estatísticas, filtros e busca funcionando
  - Edição de títulos com um clique implementada

## User Preferences

Preferred communication style: Simple, everyday language.
Subject colors required:
- Matemática (azul), História (marrom), Geografia (verde-oliva), Filosofia (cinza)
- Sociologia (violeta), Biologia (verde), Química (vermelho), Física (laranja)
- Português (preto), Inglês (azul-claro), Espanhol (amarelo), Artes (rosa)
- Educação Física (verde-limão), Literatura (roxo), Redação (vinho)