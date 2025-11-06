# Nature's Vigil - Copilot Instructions

## Project Overview
**Nature's Vigil** is a static single-page website showcasing an AI-powered computer vision system for real-time littering detection in Bangladesh. The project is not a Python/ML codebase—it's a web marketing/presentation site. The actual ML system exists conceptually; this repository is GitHub Pages hosting.

**Repository Type**: Static HTML site  
**Primary File**: `index.html` (721 lines, all-in-one HTML+CSS+structure)  
**Key Context**: See `QWEN.md` for complete technical and business architecture details

---

## Critical Architecture: The Website Structure

### Single File Design
- **`index.html`**: Monolithic file containing navigation, hero section, problem statement, solution description, tech stack explanation, impact/vision, team profiles, business models, and CTA
- **CSS Variables**: Extensive use of CSS custom properties for theming (primary green, secondary blue, spacing, shadows)
- **No JavaScript**: Pure HTML/CSS – entirely static, no interactivity beyond hover states
- **Responsive Design**: Mobile-first breakpoints at 992px, 768px, and 480px media queries

### Content Sections (in order)
1. **Header + Navigation**: Logo, sticky positioning, "Learn More" CTA
2. **Hero**: Logo, title, subtitle, primary CTA
3. **Problem Section** (`#problem`): Statistics on Bangladesh waste (31% recycling rate, 25,000+ tonnes daily)
4. **Solution Section** (`#solution`): Six-step system workflow with feature list
5. **Technology Section** (`#technology`): Two-stage architecture (YOLO v8 detection + MediaPipe pose + Temporal CNN), system diagram
6. **Impact/Vision Section** (`#impact`): Environmental targets, market size ($3.7B by 2026), strategic alignment
7. **Team Section** (`#team`): Two team members (CEO, CTO) with photo references from `Team Member/` folder
8. **Business Models Section** (`#business`): Three revenue streams (Licensing, SaaS, Data Analytics)
9. **CTA Section** (`#cta`): Cleantech competition link
10. **Footer**: Copyright notice

---

## Key Technical Patterns

### CSS Architecture
- **Root Variables**: All colors, shadows, spacing, and transitions defined at `:root`
- **Flexbox-first layouts**: `.container`, `.content-container`, `.tech-stack`, `.business-models`
- **Grid for repeating items**: `.team-grid` and `.business-models` use `grid-template-columns: repeat(auto-fit, minmax(...))`
- **Consistent sizing**: Max-width 1200px (`--max-width`), 90% width container for responsiveness
- **Card pattern**: `.stat-card`, `.model-card`, `.team-member` all follow same hover (transform Y-10px) and shadow patterns

### Typography & Spacing
- Segoe UI font stack throughout
- Title hierarchy: `h1` (3rem hero) → `.section-title` (2.5rem) → `h3` (1.8rem text-content)
- Consistent margin-bottom: 20px between elements
- Padding standardization: 100px vertical for sections, 20px horizontal for containers

### Color Scheme (Reference `QWEN.md` context)
- **Primary (Green)**: `#2e7d32` (environmental theme)
- **Primary Light**: `#60ad5e`
- **Primary Dark**: `#1b5e20`
- **Secondary (Blue)**: `#1976d2` (accent, team roles)
- **Backgrounds**: White, light-gray, light (`#f5f5f5`)

---

## Developer Workflows

### Local Development
```bash
# Start local server (any HTTP server works – pure static HTML)
python -m http.server 8000
# Or: npx http-server
# Then open: http://localhost:8000
```

### Content Changes
- **Edit directly in `index.html`**: No build process, no compilation needed
- **Asset updates**: Replace `Logo.png` or images in `Team Member/` folder (ensure path references match)
- **Data updates**: Change statistics, team members, or model details directly in HTML content

### Deployment
- Repository uses GitHub Pages: commits to main branch trigger automatic deployment to `natures-vigil.github.io`
- No action files or workflows needed – GitHub Pages auto-publishes

---

## Project-Specific Conventions

### Referencing External Resources
- Team member images: Use relative path `Team Member/[Filename]` exactly (path includes space)
- Logo: `Logo.png` at root
- External link example: Cleantech competition link in CTA uses `target="_blank"`

### Data Structure for Common Edits
- **Statistics**: Wrapped in `.stat-card` → `.stat-value` (large number) + `.stat-label` (description)
- **Tech stack**: Items in `.tech-stack` use `.tech-item` class
- **Business models**: Grid-based cards with `.model-icon` (emoji), `.model-title`, and paragraph description

### Styling New Elements
When adding content, follow these patterns:
- Use existing CSS variables (never hardcode colors)
- Apply hover states with `transform: translateY(-10px)` for cards
- Maintain 40px gap in flex layouts
- Ensure responsive behavior with `flex-wrap: wrap` and `min-width` constraints

---

## Integration Points & External References

### Linked Resources
- **Cleantech Competition**: `https://www.plasticpath.org/page/cleantech-accelerator.html` (in CTA section)
- **Team Photos**: Must exist in `Team Member/` folder with exact filenames:
  - `Swikrity Barman (CEO).jpg`
  - `Fahmid Hasan (CTO).jpg`

### Important Context (See `QWEN.md` for full details)
- **System Architecture**: YOLO v8 + MediaPipe + Temporal CNN (not implemented here – conceptual)
- **Deployment Target**: NVIDIA Jetson Xavier NX
- **Performance Metrics**: 30-60 FPS object detection, 150ms action recognition latency, 90%+ precision
- **Market Context**: Bangladesh waste 3.7B market by 2026; 50 cities addressable market

---

## When Editing or Adding Features

### Common Tasks
1. **Update statistics**: Find `.stat-value` and `.stat-label` pairs
2. **Modify team members**: Update img `src` and `alt` attributes in `.team-member` cards
3. **Change colors**: Edit CSS variables in `:root` (affects whole site)
4. **Adjust responsive breakpoints**: Search `@media` queries (currently 992px, 768px, 480px)
5. **Add new section**: Copy existing section structure (container → content-container with text-content + image-content)

### File Organization Reminders
- All HTML in `index.html` (don't split into separate files without discussion)
- CSS inline in `<style>` tag – no external stylesheets
- No JavaScript – keep it pure HTML/CSS
- Images referenced from root or `Team Member/` folder only

---

## Non-Applicable Patterns
- **No build process**: No npm scripts, Webpack, or compilation
- **No database**: Purely static content
- **No testing framework**: Not a software project with tests
- **No backend**: GitHub Pages hosting only
- **No component reuse libraries**: Everything hand-coded

---

## Quick Reference
- **Main file to edit**: `index.html`
- **Documentation**: `QWEN.md` (business/technical context)
- **Team photos**: `Team Member/` folder (space in folder name – exact path matters)
- **Logo**: `Logo.png` (root)
- **Deployment**: Automatic on main branch push (GitHub Pages)
- **No secrets/env vars needed**: Pure static content
