# 🚀 Pulse

Pulse is a modern SaaS monitoring tool designed to deliver real-time insights from your applications directly to your Discord server. Get instant notifications for sales, new user sign-ups, revenue milestones, and any other custom event you want to track.

## ✨ Features

- **Real-time Discord Alerts**: Get instant notifications for critical events like sales, new user sign-ups, and revenue milestones, beautifully formatted for Discord.
- **Modern Frontend**: A sleek and responsive landing page built with Next.js and styled with Tailwind CSS.
- **Engaging UI**: Smooth animations and transitions powered by Framer Motion, including elements that animate into view on scroll.
- **Secure Authentication**: Robust and easy-to-use user authentication handled by Clerk.
- **Edge-First API**: A fast and scalable backend built with Hono, running on the edge for low latency.
- **Type-Safe Database**: Data persistence managed with Prisma, connected to a serverless Postgres database from Neon.

## 🛠️ Tech Stack

- **Framework**: [Next.js](https://nextjs.org/) (App Router)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Authentication**: [Clerk](https://clerk.com/)
- **Animation**: [Framer Motion](https://www.framer.com/motion/)
- **API**: [Hono](https://hono.dev/)
- **ORM**: [Prisma](https://www.prisma.io/)
- **Database**: [Neon](https://neon.tech/)
- **UI Components**: Built with `shadcn/ui` principles (using `lucide-react`, `class-variance-authority`, and `clsx`).

## 📂 Project Structure

The project follows a feature-colocated structure within the Next.js App Router.

```
/src
├── app/                # Next.js App Router
│   ├── (landing)/      # Routes and layout for the marketing/landing page
│   ├── api/            # API routes handled by Hono
│   └── layout.tsx      # Root layout for the entire application
│
├── components/         # Shared React components
│   ├── ui/             # Re-usable, low-level UI components (Button, AnimatedList, etc.)
│   ├── discord-message.tsx # Component to render a mock Discord message
│   ├── max-width-wrapper.tsx # Centering and max-width container
│   └── navbar.tsx      # Application navigation bar
│
├── lib/                # Utility functions and libraries
│   ├── client.ts       # Type-safe client for Hono API
│   └── utils.ts        # General utility functions like cn()
│
├── server/             # Hono backend server logic
│   ├── __internals/    # Core server setup (j, procedure, router)
│   ├── routers/        # API routers for different resources (e.g., post-router.ts)
│   └── procedures.ts   # tRPC-like procedures for public/protected routes
│
└── db.ts               # Prisma client setup with Neon database adapter
```

## 🏁 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

- Node.js (v18.x or later recommended)
- npm, pnpm, or yarn

### Installation

1.  **Clone the repository:**

    ```sh
    git clone https://github.com/your-username/pulse.git
    cd pulse
    ```

2.  **Install dependencies:**
    ```sh
    npm install
    ```

### Environment Variables

Create a `.env.local` file in the root of your project and add the following environment variables. You can get these from your respective service dashboards.

```env
# Neon Database URL (for Prisma)
DATABASE_URL="your_neon_database_connection_string"

# Clerk Authentication Keys
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="your_clerk_publishable_key"
CLERK_SECRET_KEY="your_clerk_secret_key"

# Optional: Redis for caching (if you set it up)
# See src/server/__internals/db/cache-extension.ts
REDIS_URL="your_upstash_redis_url"
REDIS_TOKEN="your_upstash_redis_token"
```

### Running the Development Server

Start the development server with:

```sh
npm run dev
```

Open http://localhost:3000 with your browser to see the result. You can start editing the page by modifying `src/app/(landing)/page.tsx`. The page auto-updates as you edit the file.
