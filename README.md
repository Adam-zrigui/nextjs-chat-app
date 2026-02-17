# Next.js Chat App

A real-time chat application built with Next.js, featuring friend requests, messaging, and real-time notifications.

## Tech Stack

### Frontend
- **[Next.js 13.2.4](https://nextjs.org/)** - React framework with App Router for file-based routing and server-side rendering
- **[React 18.2.0](https://react.dev/)** - UI library for building interactive components
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe JavaScript for better code quality
- **[Tailwind CSS](https://tailwindcss.com/)** - Utility-first CSS framework for styling
- **[@headlessui/react](https://headlessui.com/)** - Unstyled, accessible components
- **[Lucide React](https://lucide.dev/)** - Icon library with React components
- **[React Hot Toast](https://react-hot-toast.com/)** - Toast notifications
- **[React Loading Skeleton](https://www.npmjs.com/package/react-loading-skeleton)** - Skeleton loaders for better UX during data fetching
- **[React Textarea Autosize](https://www.npmjs.com/package/react-textarea-autosize)** - Auto-expanding textarea component
- **[Tailwind Merge](https://www.npmjs.com/package/tailwind-merge)** - Utility to merge Tailwind classes intelligently
- **[@tailwindcss/forms](https://github.com/tailwindlabs/tailwindcss-forms)** - Tailwind form styles plugin

### Backend & APIs
- **[Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)** - Serverless functions for backend logic
- **[NextAuth.js 4.20.1](https://next-auth.js.org/)** - Authentication and authorization library
- **[Google OAuth](https://developers.google.com/identity/protocols/oauth2)** - Third-party authentication provider

### Database & Storage
- **[Upstash Redis](https://upstash.com/)** - Serverless Redis database for session management and data storage
- **[@next-auth/upstash-redis-adapter](https://authjs.dev/reference/adapters/upstash-redis)** - Adapter connecting NextAuth.js with Upstash Redis

### Real-time Communication
- **[Pusher](https://pusher.com/)** - Real-time messaging platform using WebSockets
- **[pusher-js](https://github.com/pusher/pusher-js)** - Client-side Pusher library for subscribing to real-time events

### Form Management & Validation
- **[React Hook Form](https://react-hook-form.com/)** - Performant form management library
- **[@hookform/resolvers](https://github.com/react-hook-form/resolvers)** - Schema resolvers for form validation
- **[Zod](https://zod.dev/)** - TypeScript-first schema validation library

### Utilities
- **[Axios](https://axios-http.com/)** - HTTP client for making API requests
- **[date-fns](https://date-fns.org/)** - Modern date utility library
- **[nanoid](https://github.com/ai/nanoid)** - Tiny, secure URL-friendly unique string ID generator
- **[class-variance-authority](https://cva.style/)** - Type-safe CSS-in-JS with class variants
- **[clsx](https://github.com/lukeed/clsx)** - Conditional className utility

### Development Tools
- **[TypeScript 4.9.5](https://www.typescriptlang.org/)** - Static type checking
- **[ESLint](https://eslint.org/)** - Code quality and style checker
- **[PostCSS](https://postcss.org/)** - CSS transformation tool
- **[Autoprefixer](https://autoprefixer.github.io/)** - Automatically add vendor prefixes to CSS
- **[pnpm](https://pnpm.io/)** - Fast, disk space efficient package manager

## Project Structure

```
src/
├── app/                    # Next.js App Router
│   ├── (auth)/            # Authentication routes (login)
│   ├── (dashboard)/       # Dashboard routes (protected)
│   │   └── dashboard/     # Main dashboard with chat features
│   │       ├── add/       # Add friend feature
│   │       ├── chat/      # Individual chat conversations
│   │       └── requests/  # Friend requests management
│   ├── api/               # API routes
│   │   └── friends/       # Friend-related endpoints
│   │       ├── accept/
│   │       ├── add/
│   │       └── deny/
│   │   └── message/       # Messaging endpoints
│   │       └── send/
│   ├── globals.css        # Global styles
│   └── layout.tsx         # Root layout component
├── components/            # Reusable React components
│   ├── AddFriendButton.tsx
│   ├── ChatInput.tsx
│   ├── FriendRequests.tsx
│   ├── Messages.tsx
│   ├── SidebarChatList.tsx
│   ├── ui/               # UI components
│   └── ...
├── helpers/              # Utility helper functions
│   ├── get-friends-by-user-id.ts
│   └── redis.ts         # Redis operations
├── lib/                 # Library configurations
│   ├── auth.ts         # NextAuth configuration
│   ├── db.ts           # Database connection (Upstash Redis)
│   ├── pusher.ts       # Pusher configuration
│   ├── utils.ts        # Utility functions
│   └── validations/    # Zod validation schemas
├── types/              # TypeScript type definitions
│   ├── db.d.ts
│   ├── next-auth.d.ts
│   ├── pusher.d.ts
│   └── typings.d.ts
└── middleware.ts       # Next.js middleware

public/                  # Static assets
```

## Key Features

- **Real-time Messaging** - Instant message delivery using Pusher WebSockets
- **Google OAuth Authentication** - Secure login with Google accounts
- **Friend Management** - Add, accept, and deny friend requests
- **Chat History** - Persistent message storage in Redis
- **Real-time Notifications** - Toast notifications for incoming messages and friend requests
- **Responsive Design** - Mobile-first UI with Tailwind CSS
- **Type Safety** - Full TypeScript support throughout the application

## Getting Started

1. Install dependencies:
   ```bash
   pnpm install
   ```

2. Set up environment variables in `.env.local`:
   ```
   GOOGLE_CLIENT_ID=your_google_client_id
   GOOGLE_CLIENT_SECRET=your_google_client_secret
   UPSTASH_REDIS_REST_URL=your_redis_url
   UPSTASH_REDIS_REST_TOKEN=your_redis_token
   PUSHER_APP_ID=your_pusher_app_id
   NEXT_PUBLIC_PUSHER_APP_KEY=your_pusher_key
   PUSHER_APP_SECRET=your_pusher_secret
   NEXTAUTH_SECRET=your_nextauth_secret
   ```

3. Run the development server:
   ```bash
   pnpm dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser
