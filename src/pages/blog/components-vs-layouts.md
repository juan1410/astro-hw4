---
title: "Astro Components vs Layouts"
description: "Learning how and when to use components and layouts in Astro"
pubDate: 2025-11-19
author: Juan Perez
layout: ../../layouts/BlogLayout.astro
---

Here is a very short description on how I found and managed the **differences between components and layouts**.

They both use `.astro` files. They both can accept props. They both help template your site. So what's the difference? Here's what I learned.

---

## What Are Components?

**Components** in Astro don’t control document structure — they simply help you write code that must be repeated.

In my project, I created a component called `Header.astro` containing the following code:

```astro
    <header>
        <nav>
            <a href="/">Juan Perez</a>
            <ul>
                <a href="/blog/">Blog</a>
                <a href="/resources/">Resources</a>
            </ul>
        </nav>
    </header>
```
This component appears across multiple pages and makes updating code much easier.

## What Are Layouts?

Layouts, on the other hand, can be used to wrap around entire pages and help maintain HTML structure across the site.

My default layout (BaseLayout.astro) looks like this:

```astro
    ---
    import Header from "../components/Header.astro";
    import Footer from "../components/Footer.astro";
    const { title } = Astro.props;
    ---

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>{title}</title>
        <link rel="stylesheet" href="/src/styles/global.css">
    </head>

    <body>
        <Header />
        <main>
            <slot />
        </main>
        <Footer />
    </body>
    </html>
```

Every page using this layout automatically gets the same structure — making layouts in Astro very helpful with structuring similar files.