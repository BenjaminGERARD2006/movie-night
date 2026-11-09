1. In which file are the <html> and <body> tags?

They are defined in app/layout.tsx. This file is the main layout of the application and wraps all the pages.

2. Which file renders the page at /?

The homepage is rendered by app/page.tsx. In Next.js, this file represents the root URL (/).

3. Which folder is for images and other static files, and how do you reference them?

The public/ folder stores static files such as images, icons and SVGs. These files can be accessed directly from the root URL. For example, public/next.svg can be accessed using /next.svg.

4. What is tsconfig.json doing in your project?

The tsconfig.json file contains the TypeScript configuration. It defines how TypeScript checks the code and manages things like imports and compiler options.

5. What does @/* mean in tsconfig.json? Write an import that uses it.

@/* is an import alias that points to the project root. It allows us to import files without writing long relative paths.

Example:
import Header from "@/components/Header";

6. What does app/layout.tsx import from next/font/google, and what does Next.js do with it at build time?

It imports a Google Font using next/font/google. The exact font depends on the configuration in app/layout.tsx. Next.js downloads and optimizes the font during the build process so it can be served locally.

7. What's the difference between layout.tsx and page.tsx?

layout.tsx defines the structure shared between pages, while page.tsx contains the actual content displayed for a specific route.

8. Where would you put a navbar that appears on every page?

I would put the navbar inside app/layout.tsx because the root layout is shared across all pages. This avoids having to write the same navbar code multiple times.

9. What is globals.css for, and where is it imported?

globals.css contains the general styles used throughout the application. It also imports Tailwind CSS. It is imported inside app/layout.tsx, making the styles available across the website.

10. What is AGENTS.md, and does your app need it to run?

AGENTS.md contains instructions and guidelines for AI coding agents working on the project. It helps them understand the project structure and follow the correct coding practices. The application does not need this file to run.