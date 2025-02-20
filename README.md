# Dynamically Added Tailwind Classes Purged During Build

This repository demonstrates a common issue encountered when using Tailwind CSS with dynamic class assignments in frameworks like Vue.js.  The problem arises because Tailwind's PurgeCSS optimization removes unused CSS classes, which can inadvertently remove classes only applied dynamically during runtime. 

## Bug Report

The `bug.vue` file shows a simple component with a conditionally applied Tailwind class.  Due to how PurgeCSS works during the build process, the class might be removed, leading to unexpected styling behavior.  In this example, if the class is not present in the initial render, the class will be missing on runtime.

## Solution

The `bugSolution.vue` file presents a few solutions to address this issue:

* **Whitelist the classes:** Add the classes to the `purge` option's whitelist in your Tailwind config.
* **Use `@apply`:** Directly apply the styles to avoid using classes and relying on PurgeCSS.
* **Use a default class:** Add a default class to the element that ensures at least one class will be present regardless of the dynamic condition.

This repository aims to illustrate the problem and provide practical solutions to ensure your dynamically styled components work consistently with Tailwind CSS.