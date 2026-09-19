# Website Audit, Optimization & SEO/GEO Toolkit

A structured workflow for auditing, understanding, optimizing, securing, and validating a website.

This toolkit combines:

- Website architecture and codebase auditing
- SEO optimization
- Generative Engine Optimization (GEO)
- Performance optimization
- Image compression
- AI-agent readiness
- Security and code-quality review
- Final verification and regression checks

The workflow is designed to make **targeted, technically justified improvements without breaking existing functionality or changing the visual identity unnecessarily**.

---

# 📋 Complete Workflow

```text
┌──────────────────────────┐
│ 1. Inspect Website       │
│    & Understand Stack    │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 2. Audit Code & Structure│
│    Security / Quality    │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 3. SEO + GEO Audit       │
│    Search + AI Engines   │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 4. Performance Testing   │
│    Lighthouse / Speed    │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 5. Optimize Assets       │
│    Images / CSS / JS     │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 6. Implement Fixes       │
│    Minimal Safe Changes  │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 7. Verify Everything     │
│    Build / Routes / SEO  │
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ 8. Final Audit & Report  │
└──────────────────────────┘
```

---

# 1. 🔍 Website Inspection & Understanding

## Purpose

The first step is to understand the existing website before modifying anything.

The master audit requires inspecting the complete project structure, configuration, pages, shared CSS/JS, APIs, SEO files, PWA files, and agent-discovery files before making changes.

## What it checks

- Project structure
- HTML pages
- CSS architecture
- JavaScript architecture
- Configuration files
- Routing and rewrites
- APIs
- SEO configuration
- Sitemap
- Robots.txt
- PWA functionality
- Offline functionality
- Agent-discovery files
- Localized pages
- Assets
- Existing tools and calculators

## Why it is important

Do not immediately rewrite or refactor the website.

The existing architecture may already contain important functionality that must remain intact, such as:

- Routing
- SEO
- PWA
- Offline mode
- Theme switching
- Calculators
- Games
- APIs
- Multilingual pages
- Agent discovery

The source workflow explicitly requires **inspection before editing** and prioritizes preserving working functionality.

---

# 2. 🧠 Understand the Website Architecture

## Purpose

Identify exactly how the website works before deciding how to optimize it.

For a static website, the audit should determine:

```text
HTML
 ↓
Shared CSS
 ↓
Shared JavaScript
 ↓
DOM / localStorage
 ↓
Optional /api/* endpoints
 ↓
Vercel deployment
```

The audit identifies page entry points, formulas, validation, outputs, localStorage usage, error handling, SEO metadata, and shared components.

## What it is used for

This stage prevents incorrect assumptions such as:

- Assuming the website uses React when it is vanilla HTML/CSS/JS
- Adding a build system unnecessarily
- Replacing existing routing
- Duplicating existing shared code
- Breaking existing APIs
- Removing PWA functionality

---

# 3. 🛡️ Security & Code Quality Audit

## Purpose

Find real security and maintainability problems before making optimization changes.

The security review is performed as a separate audit and prioritizes security first.

## Checks

### Security

- Hardcoded API keys
- Secrets
- Tokens
- Passwords
- Missing input validation
- XSS risks
- Unsafe `eval`
- Unsafe HTML injection
- Broken authentication
- Sensitive information in URLs
- Sensitive information in localStorage
- Excessive CORS permissions

### Dependencies

Check:

- Installed packages
- Current versions
- Latest versions
- Vulnerabilities
- Lockfile consistency

### Code quality

Check for:

- Duplicated logic
- Dead code
- Unused variables
- Unused imports
- Long functions
- Missing error handling
- Obvious performance problems

The goal is **not** to rewrite working code unnecessarily. The source specifically recommends the smallest change that solves the problem.

---

# 4. 🔎 SEO Optimization

## Purpose

Improve the website's visibility in traditional search engines such as Google and Bing.

SEO focuses on helping pages appear as useful search results and improving:

- Crawling
- Indexing
- Rankings
- Click-through rate
- Page relevance

The SEO/GEO source defines SEO as optimization for traditional search results and recommends one clear purpose per URL, correct canonicals, structured metadata, and appropriate schema. 
## What is checked

- `<title>`
- Meta description
- H1/H2/H3 structure
- Canonical URLs
- Robots directives
- Sitemap
- Open Graph
- Twitter metadata
- JSON-LD
- Breadcrumbs
- FAQ schema
- Organization/Person schema
- Image alt text
- Internal links
- URL structure
- Language attributes

## SEO principle

Each page should have a clear purpose.

Example:

```text
Homepage
    ↓
Category + main value proposition

Feature page
    ↓
Specific functionality

Guide
    ↓
Informational search intent

Comparison
    ↓
Commercial comparison intent

Tool
    ↓
Specific utility / calculation
```

---

# 5. 🤖 Generative Engine Optimization — GEO

## Purpose

Optimize website content so AI answer engines can understand the website, identify its entity, extract useful information, and potentially cite it.

GEO is different from traditional SEO. SEO focuses primarily on ranked search results, while GEO focuses on being named or cited within generated answers.

Target engines in the source include:

- ChatGPT
- Claude
- Perplexity
- Gemini
- Copilot
- Google AI Overviews

## GEO Citation Trinity

Every important page should provide:

### 1. Identity

The AI system should clearly understand:

```text
Who are you?
What do you do?
Who is it for?
```

### 2. Extractability

Important information should be easy to extract from the HTML.

Use:

- Question-based headings
- Direct answers
- FAQ sections
- Tables
- Concrete facts
- Short self-contained paragraphs

### 3. Corroboration

Important claims should not exist only on the website.

Build supporting references through legitimate external sources and profiles.

---

# 6. 📝 GEO Content Structure

Important sections should follow an answer-first structure:

```text
Question / Topic
        ↓
Direct answer
        ↓
Strong supporting fact
        ↓
Details
        ↓
Examples / edge cases
        ↓
Optional CTA
```

The source recommends putting the direct answer within approximately the first 40–60 words of an important section and keeping information self-contained.

## Useful GEO content

- TL;DR blocks
- FAQ sections
- Comparison tables
- Pricing information
- Concrete capabilities
- Concrete limitations
- How-to guides
- Integration guides
- Security information

## Avoid

- Keyword stuffing
- Fake certifications
- Fake reviews
- Unsupported claims
- Thin translated pages
- Answers hidden entirely behind JavaScript
- Duplicate pages

---

# 7. 🗺️ AI Crawler & Agent Readiness

## Purpose

Make the website technically understandable and accessible to AI agents and crawlers.

The GEO workflow recommends reviewing crawler access, sitemap configuration, canonical URLs, structured data, and `llms.txt`.

## Important components

```text
robots.txt
      +
sitemap.xml
      +
JSON-LD
      +
llms.txt
      +
.well-known/
      +
clean HTML
      +
canonical URLs
```

## Agent discovery

Depending on the website architecture, useful discovery resources may include:

- AI catalog
- Agent card
- API catalog
- OpenAPI
- MCP server card
- OAuth metadata
- `llms.txt`

The master project architecture specifically preserves `.well-known` agent-discovery resources and API metadata.

---

# 8. ⚡ Website Performance Optimization

## Purpose

Identify the actual causes of slow performance instead of applying generic optimizations.

The performance audit focuses on server response time, redirects, blocking resources, duplicated requests, unnecessary API calls, routing, and asset loading.

## Main areas

### Initial Server Response Time

Check:

- Root document response time
- Server-side processing
- API calls before rendering
- Unnecessary server operations
- Caching only when justified

### Redirects

Check for chains such as:

```text
HTTP
 ↓
HTTPS
 ↓
www
 ↓
non-www
 ↓
path
```

The goal is to make public URLs reach their final destination with the minimum necessary redirects.

### Blocking resources

Check:

- CSS
- JavaScript
- Fonts
- Images
- Third-party resources

### Duplicate requests

Identify:

- Repeated API calls
- Duplicate assets
- Duplicate CSS
- Duplicate JavaScript
- Unnecessary network requests

---

# 9. 🎞️ Animation Performance

For animated interfaces, especially Hero sections, optimize for smooth rendering and low main-thread usage.

The optimization requirements recommend:

- `requestAnimationFrame`
- Passive event listeners
- `transform`
- `opacity`
- `translate3d()`
- GPU acceleration
- `IntersectionObserver`
- `prefers-reduced-motion`
- Cached DOM references
- Minimal DOM complexity
- No unnecessary animation libraries

Avoid animating layout-triggering properties such as:

```text
top
left
width
height
margin
```

Use transform-based animation instead.

## Responsive targets

Verify:

```text
360px
768px
1024px
1440px
```

Also verify:

- No horizontal overflow
- Mobile performance
- Reduced-motion behavior
- Hero visibility before JavaScript loads
- Correct RTL behavior



---

# 10. 🖼️ Image Compression

## Tool

### Compress Image to 100 KB

https://image.pi7.org/compress-image-to-100kb

## What it is used for

Reduce image file size while keeping acceptable visual quality.

Useful for:

- Hero images
- Portfolio images
- Project screenshots
- Certificates
- Thumbnails
- Blog images
- Decorative images

## Typical workflow

```text
Original Image
      ↓
Check dimensions
      ↓
Compress
      ↓
Target smaller file size
      ↓
Replace optimized asset
      ↓
Test visual quality
      ↓
Run performance test
```

The website-tool list identifies this tool specifically for reducing image size and improving page performance.

---

# 11. 🚀 Website Speed Testing

## Tool

### VeerHost Website Speed Test

https://veerhost.com/ar/website-speed-test/

## What it is used for

Measure website loading performance and identify potential performance problems.

Use it after optimization to compare:

```text
BEFORE
   ↓
Performance test
   ↓
Fix problems
   ↓
AFTER
   ↓
Performance test again
```

The uploaded website-tools list identifies it as a website performance and loading-speed testing tool.

---

# 12. 🤖 AI Agent Readiness Test

## Tool

### Is It Agent Ready?

https://isitagentready.com/

## What it is used for

Check whether a website provides the technical and content signals needed for AI-agent interaction and discovery.

Use it as an additional validation step after implementing:

- Agent discovery
- Structured metadata
- Machine-readable information
- API documentation
- AI crawler accessibility
- Clear website identity

The uploaded tools list identifies this service specifically for checking whether a website is optimized and ready for AI agents.

---

# 13. 🧹 Code Cleanup

## Purpose

Remove unnecessary technical debt without changing working behavior.

The cleanup stage focuses on:

- Duplicate code
- Dead code
- Unused variables
- Unused imports
- Unnecessary files
- Debugging code
- Duplicate CSS
- Duplicate JavaScript
- Unnecessary abstractions

The source specifically recommends practical cleanup and avoiding rewrites simply for the sake of making code "cleaner."

## Preferred approach

```text
Find duplication
      ↓
Determine if it causes maintenance problems
      ↓
Reuse existing common code
      ↓
Make the smallest safe change
      ↓
Verify behavior
```

---

# 14. ♿ Accessibility

Accessibility should be preserved throughout optimization.

Check:

- Semantic HTML
- One H1 per page
- Correct heading hierarchy
- Form labels
- Image `alt`
- Keyboard navigation
- Focus states
- Button labels
- Color contrast
- Accessible navigation
- Calculator usability
- Game keyboard controls

The master audit explicitly includes semantic structure, labels, focus visibility, contrast, and keyboard operation.

---

# 15. 🔐 Security Headers & Input Safety

Preserve important security controls such as:

```text
X-Content-Type-Options
X-Frame-Options
Referrer-Policy
Permissions-Policy
```

Calculator and tool inputs should be validated.

User-controlled values should not be inserted into HTML unsafely. Prefer safe DOM APIs such as:

```javascript
textContent
```

instead of unsafe HTML injection.



---

# 16. 🧪 Verification

Never assume that a modification worked.

After implementation, verify:

### Code

```bash
node --check api/*.js middleware.js
```

### Local website

Test:

```text
/
Mohamed - *.html
/sites/*.html
/offline.html
/sitemap.xml
/manifest.webmanifest
/.well-known/ai-catalog.json
```

### Browser

Check:

- Console errors
- Mobile layout
- Desktop layout
- Navigation
- Theme toggle
- Calculators
- Games
- Forms
- Images
- Fonts
- APIs
- Offline mode

### SEO

Verify:

- Canonicals
- Sitemap
- Robots
- JSON-LD
- Metadata
- Open Graph
- Internal links

### Performance

Run:

- Lighthouse
- Chrome DevTools Performance
- Website speed test

The master workflow requires actual verification and explicitly says not to claim something was tested if it was not tested.

---

# 17. 📊 Before vs After Measurement

Always compare measurable results.

| Metric | Before | After |
|---|---:|---:|
| Performance | — | — |
| Page Size | — | — |
| Requests | — | — |
| Load Time | — | — |
| LCP | — | — |
| CLS | — | — |
| INP | — | — |
| Server Response | — | — |
| Image Size | — | — |
| Console Errors | — | — |

Do not claim an improvement unless the corresponding measurement was actually performed.

---

# 18. 🔄 Recommended Execution Order

Use this order for future website optimization work:

### Phase 1 — Understand

1. Detect the technology stack.
2. Read the project structure.
3. Inspect configuration.
4. Inspect pages.
5. Inspect shared CSS/JS.
6. Inspect APIs.
7. Inspect SEO and PWA files.

### Phase 2 — Audit

8. Security audit.
9. Code-quality audit.
10. SEO audit.
11. GEO audit.
12. Accessibility audit.
13. Performance audit.

### Phase 3 — Measure

14. Run Lighthouse.
15. Run website speed test.
16. Check browser console.
17. Check network requests.
18. Record baseline metrics.

### Phase 4 — Optimize

19. Fix critical security issues.
20. Fix real performance bottlenecks.
21. Optimize images.
22. Reduce duplicate CSS/JS.
23. Improve SEO.
24. Improve GEO.
25. Improve accessibility.
26. Clean unnecessary code.

### Phase 5 — Verify

27. Test routes.
28. Test functionality.
29. Test responsive layouts.
30. Test SEO metadata.
31. Test PWA/offline functionality.
32. Test AI-agent discovery.
33. Run Lighthouse again.
34. Compare before/after results.

### Phase 6 — Report

35. Problems found.
36. Files changed.
37. Changes made.
38. Performance impact.
39. SEO/GEO improvements.
40. Security changes.
41. Remaining warnings.
42. Recommended next steps.

---

# 19. 🧩 Tool Map

| Tool | Main Purpose | When to Use |
|---|---|---|
| **Is It Agent Ready** | AI-agent readiness | After GEO/agent implementation |
| **VeerHost Speed Test** | Website loading performance | Before and after performance fixes |
| **Compress Image to 100 KB** | Image optimization | When images are unnecessarily large |
| **Lighthouse** | Performance, SEO, A11y, Best Practices | Baseline + final validation |
| **Chrome DevTools** | Runtime/network/performance debugging | When investigating actual bottlenecks |
| **Code Audit Prompts** | Security + maintainability | Before making large changes |
| **SEO/GEO Prompt** | Search + AI visibility | SEO/GEO implementation |
| **Master Audit Prompt** | Complete project workflow | Full website audit |

---

# 20. 🎯 Core Principles

### Inspect before editing

Understand the existing system before making changes.

### Fix root causes

Do not apply generic optimizations just because a tool reports a warning. Identify the actual technical cause first.

### Preserve functionality

Do not break:

- Existing routes
- SEO
- PWA
- Offline mode
- APIs
- Calculators
- Games
- Localization
- Agent discovery



### Prefer minimal changes

Reuse existing architecture instead of introducing unnecessary frameworks, dependencies, or abstractions.

### Measure before and after

Performance improvements should be demonstrated through actual measurements.

### Never fabricate

Do not invent:

- Certifications
- Reviews
- Profiles
- Statistics
- Performance results
- SEO results
- AI citations

The GEO source explicitly prohibits fake certifications, fake reviews, and fake profiles.

---

# 21. ✅ Final Goal

The final website should be:

```text
                    WEBSITE
                       │
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
      SEO             GEO        PERFORMANCE
        │              │              │
   Google/Bing      AI Engines     Fast Loading
        │              │              │
        └──────────────┼──────────────┘
                       ↓
                  ACCESSIBILITY
                       ↓
                    SECURITY
                       ↓
                MAINTAINABILITY
                       ↓
                VERIFIED WEBSITE
```

The objective is not simply to make a website "score higher."

The objective is to build a website that is:

- Fast
- Search-friendly
- AI-readable
- Accessible
- Secure
- Maintainable
- Responsive
- Functionally stable
- Properly documented
- Measurably improved