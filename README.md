# SkillCraft Technology — Task 01

A responsive landing page for the SkillCraft Technology Task 01 assignment. The page demonstrates a fixed navigation menu that stays visible while scrolling, changes into a darker blurred `.scrolled` state after 50px, and exposes animated hover underlines on every navigation link.

## Features

The implementation includes semantic sections for Hero, About, Services, Projects, CTA, Contact, and Footer. The mobile layout replaces the desktop links with an accessible hamburger button, closes after selecting a link, and avoids horizontal overflow. Scroll reveal uses the browser-native `IntersectionObserver`; the contact form has a lightweight submission feedback state; and the page honors `prefers-reduced-motion`.

## Technologies

The frontend uses React only as the host for the landing page component in the provided static workspace. The actual interaction logic is beginner-friendly vanilla JavaScript modules, with CSS3 for layout and animation. No UI framework, animation library, or external runtime dependency was added for the assignment behavior.

## File structure

- `client/src/pages/Home.tsx` — semantic page structure and content.
- `client/src/styles/style.css` — visual system, layout, components, and navbar base styling.
- `client/src/styles/animations.css` — hero entrance, hover transitions, floating artwork, and scroll reveal.
- `client/src/styles/responsive.css` — tablet, mobile, and narrow-screen behavior.
- `client/src/lib/navigation.js` — fixed navbar scroll state and mobile menu state.
- `client/src/lib/animations.js` — `IntersectionObserver` scroll reveal.
- `client/src/lib/main.js` — general page initialization and contact-form feedback.
- `ideas.md` — selected Signal / Studio visual direction.

## Run locally

From the project directory, run `pnpm dev` and open the local Vite URL. The project is also ready to open in VS Code and inspect file-by-file.

## How the navbar interaction works

The navigation is fixed with `position: fixed`, so it remains visible as the page moves. `navigation.js` listens to `scroll` and toggles the `scrolled` class when `window.scrollY > 50`. The CSS for `.navbar.scrolled` adds opacity, backdrop blur, border strength, shadow, and a shorter inner height. Link hover is handled entirely in CSS: a pseudo-element expands from right to left under the label. On mobile, JavaScript toggles `.menu-open`, updates `aria-expanded`, and closes the menu after a link is selected.

## Beginner notes

`IntersectionObserver` lets the browser notify us when a `.reveal` element enters the viewport, so we do not need a heavy animation library or a scroll handler that runs constantly. CSS `transform` and `opacity` are used for motion because they are efficient to animate and do not force the browser to recalculate the layout on every frame.

live link : 

<img width="1322" height="1021" alt="image" src="https://github.com/user-attachments/assets/4471c0f7-2eae-4d8d-a56c-b89c712ddb5a" />

