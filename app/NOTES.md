Lab-1

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

Lab-2

1. In the page source, are the movie titles present for /movies? For /movies-client? Why?

For /movies, the movie titles are already in the HTML because Next.js renders the page on the server before sending it to the browser. For /movies-client, the titles are not in the initial HTML because the movies are fetched using useEffect after the page loads. The page source only shows "Loading movies...".

2. Without the force-dynamic line of Part E, you run npm run build again tomorrow, then npm start, without changing anything else. What does the "Rendered at" timestamp of /movies show, and why?

The timestamp will show the time of tomorrow's build. This is because Next.js generates the static page during npm run build. The timestamp stays the same when refreshing the page because it was generated at build time, not on every request.

3. Part E made every request to /movies about one second slower. Give one situation where force-dynamic is still the right choice, and explain why.

I would use force-dynamic for something like a live voting system where students vote for their favourite movie. The results need to be updated frequently, so rendering the page on every request makes sure users get the latest data, even if it takes a little longer to load.

4. A classmate sees [movies] rendered 6 movies in the browser console and says: "So this code runs in the browser." What do you answer, and how can you prove it?

I would explain that the code actually runs on the server because /movies is a Server Component. Next.js can display server logs in the browser console during development, but that doesn't mean the code runs there. We can prove it by checking the terminal, where the same message appears, or by disabling JavaScript and seeing that the movie list still works.

5. Which version would you choose for a public movie catalogue that changes once a week, and why?

I would choose the static version because the movie catalogue doesn't change very often. Next.js can generate the page during the build, which makes it faster for visitors because the server doesn't need to fetch the movies every time. We would just need to rebuild the website when the catalogue changes.