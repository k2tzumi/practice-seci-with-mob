# GitHub Copilot Instructions for Slidev Boilerplate

This repository is a **Slidev** template repository for creating presentation slides. Please follow these guidelines to assist with code and content creation/editing.

## GitHub Issue Workflow with Copilot Agent Mode

When starting work from a GitHub issue using Copilot Agent mode:

### Branch Creation from Issues
1. **Analyze the issue**: Read the issue title, description, and labels to understand the work scope
2. **Create descriptive branch name**: Use the format `issue-{number}-{descriptive-name}`
3. **Branch naming conventions**:
   - Use kebab-case (lowercase with hyphens)
   - Include issue number for traceability
   - Add descriptive keywords from issue title
   - Keep under 50 characters when possible

### Branch Naming Examples
- Issue #15 "Add dark theme support" → `issue-15-add-dark-theme`
- Issue #32 "Fix PDF export layout" → `issue-32-fix-pdf-export-layout`  
- Issue #8 "Update slide templates" → `issue-8-update-slide-templates`
- Issue #41 "Implement new Transform component" → `issue-41-implement-transform-component`

### Workflow Steps
1. **Branch creation**: `git checkout -b issue-{number}-{descriptive-name}`
2. **Work implementation**: Follow the development guidelines below
3. **Commit messages**: Reference issue number in commits (`fix #15: implement dark theme`)
4. **Pull request**: Create PR that links back to the original issue

## Project Overview

- **Purpose**: Create presentation slides using Slidev
- **Main file**: `slides.md` - Write slides in Slidev Markdown format
- **Output formats**: HTML (development), PDF (publishing/distribution)

## Development & Build Commands

### Basic Commands
- `make dev` - Start development server (http://localhost:3030, dependencies are automatically resolved)
- `make lint` - Technical writing text validation
- `make pdf` - Generate PDF from slides (outputs as `slides-export.pdf`)

### Quality Control
- **Text validation**: Use `make lint` to check technical writing quality
- **Visual confirmation**: Use `make pdf` to generate PDF and confirm/adjust slide appearance

## Slidev Markdown Writing Rules

### Slide Separators
Use `---` to create new slides:
```markdown
---
```

### Frontmatter (Configuration)
Configure layout, background, etc. at the beginning of slides:
```yaml
---
layout: center
background: /background-1.png
class: text-white
---
```

### Basic Structure Example
```markdown
---
theme: seriph
title: 🚀 Presentation Title
---

# 📊 Title Slide
Subtitle or introduction with visual context

---

# 💡 Content Slide
- ✅ Point 1 (completed)
- ⚠️ Point 2 (in progress)
- 🚀 Action item (upcoming)
- <logos-vue /> Built with Vue.js

---
layout: center
---

# ✨ Center-aligned Slide
📈 Growing Success
```

## Guidelines for Code Creation/Editing

### When Creating Slide Content
1. **Structure**: Focus each slide on one clear message
2. **Visual hierarchy**: Use headings (#, ##, ###) appropriately
3. **Code blocks**: Utilize syntax highlighting
4. **Diagrams**: Create diagrams using Mermaid or PlantUML
5. **Visual enhancement**: Add emojis and Iconify icons to improve readability and engagement

### Visual Enhancement with Icons and Emojis
- **Priority order**: Use emojis first, then Iconify icons when emojis are not suitable
- **Emojis first**: Prefer native emojis for general concepts (📊 📈 🚀 💡 ⚡ 🎯 ✨ 🔧 📝 ✅ ⚠️ 🆕 etc.)
- **Iconify for specifics**: Use Iconify icons for technical logos, brand symbols, and specific concepts without emoji equivalents
  ```markdown
  💡 Ideas vs <logos-vue /> Vue.js
  📊 Data vs <carbon-analytics /> Analytics dashboard
  ✅ Success vs <mdi-check-circle class="text-green-500" /> Completed task
  ```
- **Technical logos**: Always use Iconify for technology brands (`<logos-*>` collection)
- **Icon styling**: Apply UnoCSS classes for colors, sizes, and animations when using Iconify
- **Contextual usage**: Choose visual elements that reinforce the content meaning

### Common Icon Collections and Use Cases
**Use Iconify only when emojis are insufficient:**
- **Technical logos** (`logos-*`): Technology and brand logos (Vue.js, React, Python, etc.)
- **Specific UI elements** (`mdi-*`, `carbon-*`): When precise interface icons are needed
- **Business-specific icons** (`uim-*`): Professional symbols not available as emojis
- **Custom styling needs**: When specific colors or animations are required

**Emoji preference examples:**
- ✅ vs `<mdi-check />` - Use emoji
- 🚀 vs `<carbon-rocket />` - Use emoji  
- 📊 vs `<uim-analytics />` - Use emoji
- But: <logos-vue /> for Vue.js logo (no emoji equivalent)

### Styling
- **UnoCSS**: Style with utility classes
- **Scoped CSS**: Custom styles for individual slides
- **MDC Syntax**: Easy style application

### Design with PDF Output in Mind
- **Visual confirmation**: Always check PDF output with `make pdf`
- **Scale optimization**: Use Transform component (`<Transform :scale="0.8">`) to fit content optimally in slides
- **Layout**: Consider readability when printed
- **Color usage**: Ensure readability in print/monochrome display

### Transform Component for Content Scaling
Use the Transform component to optimize content size for PDF output:
```markdown
<Transform :scale="0.8">

# Your slide content
- Text content
- Images
- Tables
- Any other elements

</Transform>
```
- Adjust scale value (e.g., 0.7, 0.8, 0.9, 1.2) to fit content within one slide
- Scale entire slide content including text, images, tables, and diagrams
- Prioritize maximum readability while fitting content in PDF format
- Test different scale values with `make pdf` to find optimal size

## Recommended File Structure

### Images & Assets
- Place in `/public/` directory
- Reference in slides as `/image.png`

### Multi-file Structure
- Long presentations can be split into multiple files
- Include with `src: ./pages/filename.md`

### Notes & Comments
```markdown
<!-- This is a presenter note -->
```
Comments at the end of slides are displayed as presenter notes

## Quality Check Points

### Content Quality
1. **Text validation**: Check grammar and notation with `make lint`
2. **Structure confirmation**: Ensure logical flow
3. **Visual balance**: Appropriate amount of information per slide

### Technical Quality
1. **PDF output confirmation**: Check final appearance with `make pdf`
2. **Links & references**: Verify all images and links work correctly
3. **Responsive**: Check display on different screen sizes

## Special Features & Extensions

This template includes the following features:
- **Multiple Slidev addons**: Pre-installed extensions
- **Automatic release management**: Version management with tagpr
- **GitHub Pages publishing**: Automatic deployment
- **OGP & Google Analytics support**: Features for web publishing

## Recommended Workflow

1. **Development**: Start development server with `make dev`
2. **Editing**: Edit `slides.md` with real-time preview
3. **Text validation**: Check quality with `make lint`
4. **Visual confirmation**: Check PDF output with `make pdf`
5. **Adjustment**: Refine appearance based on PDF output
6. **Completion**: Finalize the presentation

Always prioritize the appearance in PDF output and consider the actual presentation environment display.

## Key Principles for Copilot Assistance

When providing suggestions or generating content:

1. **PDF-first approach**: Always consider how content will appear in PDF format
2. **Technical writing standards**: Follow best practices for technical documentation
3. **Slidev-specific syntax**: Use proper Slidev Markdown features and conventions
4. **Visual hierarchy**: Maintain clear information structure across slides
5. **Accessibility**: Ensure content is readable and well-structured
6. **Performance**: Consider file sizes and loading times for images and assets

## Common Patterns to Follow

### Slide Titles
- Use clear, descriptive titles with relevant emojis (🔍 Analysis, 📈 Results, 🎯 Goals)
- Maintain consistent formatting
- Consider title length for PDF display

### Content Organization
- One main concept per slide
- Use bullet points with emojis first (✅ ⚠️ 🚀), Iconify icons only when needed
- Break complex topics into multiple slides
- Use Transform component to scale content: `<Transform :scale="0.8">content</Transform>`
- Optimize scale values to fit maximum content while maintaining readability
- Add contextual emojis to section headers and key points

### Code Examples
- Include proper syntax highlighting
- Keep code blocks readable in PDF
- Provide context and explanations
- Use tech logos from Iconify for specific languages: `<logos-javascript />`, `<logos-python />`, `<logos-typescript />`
- Prefer emojis for general programming concepts: 💻 🔧 ⚙️ 🐛

### Visual Elements
- Optimize images for both web and print
- Use consistent color schemes
- Ensure adequate contrast ratios
- **Emoji-first approach**: Use emojis for general concepts, supplement with Iconify for technical specifics
- Use emoji status indicators for lists: ✅ Complete, ⚠️ In Progress, 🚀 Coming Soon, 🆕 New

Remember: The final presentation will be primarily consumed as a PDF, so all design and content decisions should prioritize PDF readability and professional appearance. Use the Transform component strategically to scale content (text, images, tables) to fit optimally within each slide while maximizing readability. Enhance text-heavy content with appropriate emojis and Iconify icons to improve visual engagement and comprehension, while maintaining professional standards.