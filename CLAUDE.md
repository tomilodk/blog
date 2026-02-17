# mappso blog

Static blog served via Nginx in Docker. Vanilla HTML/CSS, no framework.

## Blog Conventions

### Naming
- **"compozerr" is always lowercase.** Never capitalize it, even at the start of a sentence.
- Brand name "mappso" is also always lowercase.

### Links & SEO
- **Every reference to a company, product, or website must be an `<a>` tag** linking to that entity's homepage or relevant page (e.g., docs). This includes tools (Traefik, Docker, n8n), platforms (Vercel, Railway, GitHub), languages/runtimes (Bun, Node.js, TypeScript, .NET, React), and compozerr itself.
- **compozerr references** link to `https://compozerr.com`. References to specific CLI commands (like `compozerr deploy`) in prose can link to compozerr docs.
- **Post pages** (`body.post`) use **dotted underline and grey color** (`var(--text-muted)`) for links. The index page uses default solid underline styling. Post pages must have `<body class="post">`.
- Inside code blocks (`<pre><code>`), text remains as code — no `<a>` tags.

### SEO Purpose
The blog serves a dual purpose:
1. **Content** — sharing knowledge and building posts about compozerr, infrastructure, and dev workflows.
2. **SEO for compozerr and the tools ecosystem** — every post should link out to relevant tools, competitors, and related technologies. This creates topical authority and connects compozerr to the broader deployment/infrastructure landscape. Think of each post as a node in a web of related technologies — link liberally to establish context.

When writing about competitors or alternatives (Vercel, Railway, Render, Fly.io, etc.), link to them. When mentioning tools compozerr uses (Traefik, Docker, Proxmox, Let's Encrypt), link to them. This is intentional SEO strategy, not just courtesy.

### Page Structure
- Every page includes: meta description, Open Graph tags, Twitter Card tags, canonical URL, JSON-LD structured data.
- Blog index is at `/index.html`. Posts live at `/posts/<slug>/index.html`.
- Each post has a back-nav linking to the blog index: `<nav class="post-nav"><a href="/">← mappso blog</a></nav>`
- On the index page, "mappso" is an `<a>` tag linking to `https://mappso.com`.

### Adding a New Post
1. Create `src/posts/<slug>/index.html`
2. Add the post to the listing in `src/index.html` (newest first)
3. Add the URL to `src/sitemap.xml`

## Tech Stack
- Static HTML/CSS
- Newsreader serif font (custom WOFF2)
- Light/dark mode via `prefers-color-scheme`
- Nginx Alpine container on port 3000
- Deployed via compozerr (`compozerr.json`)
