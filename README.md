# Genius Terminal IQ Challenge

A themed 10-question Web3 trivia quiz in a single HTML file, deployed on Vercel.

This is a fan-made quiz page about the Genius Terminal DeFi project. The questions are about its product (cross-chain swaps, a self-custodial PerpDEX and its points campaign). The page runs entirely in the browser: there is no build step, no backend, no wallet connection and no data collection. It is a small front-end exercise covering React state, animations and responsive layout.

> Not affiliated with or endorsed by Genius Terminal. The question text is promotional copy written for the quiz and is not financial advice.

**Live demo:** https://geniustest.vercel.app

## Features

- 10 multiple-choice questions with instant feedback (a random line of praise for a correct answer, a hint for a wrong one) and a progress bar
- A score out of 200 on the final screen, plus a restart button
- A glassmorphism dark UI with gradient text, fade-in animations and a particle burst wherever you click
- A responsive layout for desktop and mobile

## How it works

```
index.html
 ├─ Tailwind CSS (Play CDN, pinned to 3.4.16)                 styling
 ├─ React 18.3.1 + ReactDOM 18.3.1 (production UMD, SRI)      UI
 ├─ @babel/standalone 7.26.10 (SRI)                           compiles the inline JSX in the browser
 └─ <script type="text/babel">                                questions[], praises[], <App/>
```

`App` keeps the current question, the score and the feedback state in React hooks. Each correct answer adds 20 points. After the last question, the result screen is shown.

## Tech stack

React 18 (UMD), JSX compiled in the browser by Babel Standalone, Tailwind CSS (Play CDN), and static hosting on Vercel.

## Project structure

```
index.html   the whole app: markup, styles, questions and React component
LICENSE      MIT
```

## Getting started

No install or build step is needed.

```bash
git clone https://github.com/furkan3152/GeniusTest.git
cd GeniusTest
# open the file directly...
open index.html            # macOS (use xdg-open on Linux)
# ...or serve it locally
python3 -m http.server 8000   # then visit http://localhost:8000
```

To deploy, import the repository into Vercel as a static site. No build command or environment variables are needed.

## Security notes

- All third-party scripts are pinned to exact versions. The React, ReactDOM and Babel builds are loaded with Subresource Integrity (`integrity` + `crossorigin`) hashes.
- No secrets, API keys or wallet interactions.
- Compiling JSX in the browser and using the Tailwind Play CDN suit a small demo. A production version would pre-compile with a bundler (for example Vite) and generate the Tailwind CSS at build time.

## License

[MIT](LICENSE)

---

Built by Furkan Akdogan ([@furkan3152](https://github.com/furkan3152))
