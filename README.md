# AI Engineering Lab Hub — source code

The private class website for the AI Engineering Lab (Club C, ages 13-16, Tuesdays 12:30-1:15 PM, Fall 2026).
Pages: Schedule (home), Teacher guides, Students, Videos, Experiments, Sub plans, Downloads.

## Open in VS Code and run it

1. Install Node.js 20 or newer (https://nodejs.org). Bun (https://bun.sh) also works.
2. In VS Code: File > Open Folder... and choose this folder.
3. Open the terminal (Terminal > New Terminal) and run:

       npm install
       npm run dev

   (or `bun install` then `bun run dev`)

4. Open the address it prints (usually http://localhost:5173/). Start at that root address and use the
   site's own menu to move between pages.

Other commands:

    npm run build      # production build into dist/
    npm run preview    # serve the production build locally
    npm run typecheck  # TypeScript check
    npm run lint       # ESLint

## Where things live

    src/data/course.ts               ALL class content: sessions, missions, exit checks, videos, tools,
                                     sub-day steps, canvas prompts, download list, suggested pacing
    src/pages/home.tsx               Schedule (home) — timeline + session detail
    src/pages/teacher-guides.tsx     Teacher guides
    src/pages/student-resources.tsx  Student resources + digital AI Engineer Log
    src/pages/videos.tsx             Videos
    src/pages/experiments.tsx        Experiments
    src/pages/sub-plans.tsx          Substitute plans
    src/pages/materials.tsx          Downloads
    src/routes.tsx                   Route + menu list (add a page = add one entry)
    src/components/semester-timeline.tsx   The semester timeline drawing
    src/components/app-shell.tsx     Header, navigation, skip link
    src/lib/store.ts                 Saved progress, notes and lab-log drafts (browser local storage)
    src/index.css                    Colors, radius and print styles (Tailwind v4 tokens)
    public/downloads/                The four Word documents served by the Downloads page

To change a date, mission, link or exit check, edit `src/data/course.ts` — every page reads from it.

## Stack

React 19, TypeScript, Vite 7, Tailwind CSS v4, shadcn/ui (Radix), react-router-dom 7, zustand,
lucide-react icons, sonner toasts. Everything is client-side; there is no server or database.
