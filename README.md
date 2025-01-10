This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

# Code Snippet Manager

A Next.js application for creating, storing, and managing code snippets. Built with Next.js 15, Prisma, TypeScript, and Monaco Editor.

## Features

- Create and store code snippets with titles
- Edit snippets with a full-featured code editor
- Delete snippets
- View all snippets in a list
- Server-side rendering and static generation
- Real-time code editing with Monaco Editor

## Tech Stack

- **Frontend**: Next.js 15, React 18, TailwindCSS
- **Backend**: Prisma with SQLite
- **Editor**: Monaco Editor (same as VS Code)
- **Language**: TypeScript
- **Styling**: TailwindCSS

## Prerequisites

- Node.js 18.18.0 or higher
- npm or yarn package manager
- Git

## Setup Instructions

1. Get started:
```bash
npx create-next-app@latest 
```

3. Set up the database:
- Create a `.env` file in the root directory
- Add the following line:
```env
DATABASE_URL="file:./dev.db"
```

4. Initialize Prisma and create the database:
```bash
npm install prisma
npx prisma init --datasource-provider sqlite
npx prisma generate
npx prisma migrate dev
√ Enter a name for the new migration: ... [name]
```

5. Run the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:3000`

## Project Structure

```
├── src/
│   ├── actions/         # Server actions for data mutations
│   ├── app/            # Next.js app router pages
│   ├── components/     # Reusable React components
│   └── db/            # Database configuration
├── prisma/
│   ├── migrations/    # Database migrations
│   └── schema.prisma  # Prisma schema
├── public/           # Static assets
└── ...config files
```

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run lint` - Run ESLint

## Database Schema

```prisma
model Snippet {
  id        Int      @id @default(autoincrement())
  title     String
  code      String
  createdAt DateTime @default(now())
}
```

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## License

MIT License

## Troubleshooting

If you encounter any issues:

1. Make sure you're using the correct Node.js version
2. Clear the `.next` cache:
```bash
rm -rf .next
```
3. Regenerate Prisma client:
```bash
npx prisma generate
```
4. Ensure all dependencies are installed:
```bash
npm install
```

## Environment Variables

Required environment variables:
- `DATABASE_URL`: Path to your SQLite database

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
