---
title: "View Transitions in Astro"
description: "Implementing View Transition API"
pubDate: 2025-11-16
author: "Juan Perez"
layout: ../../layouts/BlogLayout.astro
---

One of the new features that I have been enjoying a lot recently is the **View Transition API** which allows for smooth animated transitions when navigating between pages.

Using Astro, I found it very **easy** and **fun**.

### How I Added Transitions
Adding View Transitions took just a few lines of code:

1. At the **top of each page**, I exported a flag:
   ```js
   export const viewTransition = true;
2. Then, in my layout file, I styled the view transition targets:
    ```css
    @view-transition {
        navigation: auto;
    }

    main {
        view-transition-name: content;
    }
3. Lastly, I deployed to CloudFare and the page transitions ran very smoothly.

### Why It Matters
> This API allows us to use transitions within MPAs, without adding a single JS script.

Want to try it yourself? Check the MDN View Transition API page for some great examples which I found very useful.
