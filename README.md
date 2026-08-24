# Week 5 In-Class Project: Data-Driven Portfolio Foundation

## Project Overview

Transform your Week 3 static portfolio into a data-driven structure using JavaScript objects and arrays. This project focuses on organizing content with JavaScript data structures and generating HTML using template literals - building on the JavaScript fundamentals you learned in Chapters 2-3.

## Learning Objectives

By the end of this project, students will be able to:
1. ✅ Organize portfolio content using JavaScript objects and arrays
2. ✅ Access nested object properties and array elements
3. ✅ Use template literals to build HTML strings dynamically
4. ✅ Generate content using `document.write()` and simple loops
5. ✅ Create HTML5 forms with various input types
6. ✅ Use browser DevTools console for data exploration and debugging

## What You'll Build

**Before (Week 3):** Static HTML with hardcoded content
**After (Week 5):** Data-driven portfolio that generates content from JavaScript

### File Structure
```
week5-portfolio/
├── index.html       # HTML structure with script tags
├── style.css        # CSS styling (built on Week 3)
├── data.js          # Portfolio data in objects/arrays
└── display.js       # HTML generation logic
```

## Project Phases

### Phase 1: Data Organization (15 minutes)

#### Step 1.1: Set Up Your Data Structure
In `data.js`, you'll organize your portfolio information:

```javascript
const portfolio = {
    owner: {
        name: "Your Name",
        title: "Your Professional Title",
        email: "your.email@example.com",
        location: "Your City, State",
        bio: "Tell your story..."
    },
    
    skills: [
        "HTML5 & Semantic Markup",
        "CSS3 & Responsive Design",
        "JavaScript Fundamentals",
        "Add more skills..."
    ],
    
    projects: [
        {
            title: "Project Name",
            description: "What does this project do?",
            technologies: ["HTML", "CSS", "JavaScript"],
            completionDate: "2025-09-15",
            featured: true
        }
    ]
};
```

#### Step 1.2: Explore Your Data
Use `console.log()` to understand your data structure:

```javascript
console.log("My name:", portfolio.owner.name);
console.log("Total skills:", portfolio.skills.length);
console.log("First project:", portfolio.projects[0]);
```

### Phase 2: HTML Generation (20 minutes)

#### Step 2.1: Create Header Section
In `display.js`, use template literals to build HTML:

```javascript
let headerHTML = `
    <header>
        <h1>${portfolio.owner.name}</h1>
        <p class="tagline">${portfolio.owner.title}</p>
        <p class="location">📍 ${portfolio.owner.location}</p>
    </header>
`;

document.write(headerHTML);
```

#### Step 2.2: Generate Skills List
Use a simple for loop to create your skills section:

```javascript
let skillsHTML = '<section id="skills"><h2>My Skills</h2><ul class="skills-list">';

for (let i = 0; i < portfolio.skills.length; i++) {
    skillsHTML = skillsHTML + `<li>${portfolio.skills[i]}</li>`;
}

skillsHTML = skillsHTML + '</ul></section>';
document.write(skillsHTML);
```

#### Step 2.3: Build Projects Showcase
Create project cards from your data:

```javascript
let projectsHTML = '<section id="projects"><h2>My Projects</h2><div class="projects-grid">';

for (let i = 0; i < portfolio.projects.length; i++) {
    let project = portfolio.projects[i];
    let techList = project.technologies.join(", ");
    
    projectsHTML = projectsHTML + `
        <article class="project-card">
            <h3>${project.title}</h3>
            <p>${project.description}</p>
            <p class="tech">Technologies: ${techList}</p>
        </article>
    `;
}

projectsHTML = projectsHTML + '</div></section>';
document.write(projectsHTML);
```

### Phase 3: Enhanced Forms (15 minutes)

#### Step 3.1: HTML5 Input Types
Add various HTML5 inputs to your contact form:

```html
<!-- Text input -->
<label for="name">Name:</label>
<input type="text" id="name" name="name" required>

<!-- Email input (HTML5) -->
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>

<!-- Phone input (HTML5) -->
<label for="phone">Phone:</label>
<input type="tel" id="phone" name="phone">

<!-- Date input (HTML5) -->
<label for="start-date">Preferred Start Date:</label>
<input type="date" id="start-date" name="start-date">

<!-- Number input -->
<label for="budget">Budget (USD):</label>
<input type="number" id="budget" name="budget" min="0" step="100">
```

#### Step 3.2: Radio Buttons and Checkboxes
```html
<fieldset>
    <legend>Preferred Contact Method:</legend>
    <input type="radio" id="contact-email" name="contact" value="email">
    <label for="contact-email">Email</label>
    <input type="radio" id="contact-phone" name="contact" value="phone">
    <label for="contact-phone">Phone</label>
</fieldset>

<fieldset>
    <legend>Project Timeline:</legend>
    <input type="checkbox" id="asap" name="timeline" value="asap">
    <label for="asap">ASAP</label>
    <input type="checkbox" id="flexible" name="timeline" value="flexible">
    <label for="flexible">Flexible</label>
</fieldset>
```

### Phase 4: Console Practice (10 minutes)

#### Step 4.1: Data Analysis
Practice accessing and analyzing your data:

```javascript
// Create summary statistics
console.log("Portfolio Summary:");
console.log(`${portfolio.owner.name} has ${portfolio.skills.length} skills`);
console.log(`and ${portfolio.projects.length} projects`);

// Find featured projects
for (let i = 0; i < portfolio.projects.length; i++) {
    if (portfolio.projects[i].featured === true) {
        console.log("⭐ Featured:", portfolio.projects[i].title);
    }
}
```

#### Step 4.2: JSON Exploration
```javascript
// Convert to JSON for storage/debugging
let dataAsJSON = JSON.stringify(portfolio, null, 2);
console.log("Portfolio as JSON:", dataAsJSON);
```

## Key Concepts Used

### ✅ What You Know (Chapters 1-3)
- **Variables**: `let`, `const`, `var`
- **Data Types**: strings, numbers, booleans, arrays, objects
- **String Methods**: `.join()`, `.length`
- **Template Literals**: `` `Hello ${name}` ``
- **Object Access**: `portfolio.owner.name`
- **Array Access**: `skills[0]`, `skills.length`
- **For Loops**: Basic iteration with indices
- **Console Methods**: `console.log()`
- **Output**: `document.write()`

## Success Criteria

Your portfolio should demonstrate:
1. ✅ **Data Organization**: Content stored in logical objects/arrays
2. ✅ **Dynamic Generation**: HTML created from data using template literals
3. ✅ **Working Output**: Content displays correctly on the page
4. ✅ **Form Enhancement**: Multiple HTML5 input types working
5. ✅ **Console Usage**: Data exploration visible in browser console
6. ✅ **Personalization**: Your own content and information

## Tips for Success

### Data Organization
- Keep objects flat and simple
- Use descriptive property names
- Store repeating items (skills, projects) as arrays
- Use consistent data types

### HTML Generation
- Build HTML strings step by step
- Use `+` to concatenate strings
- Test template literals with `console.log()` first
- Keep generated HTML valid and semantic

### Debugging
- Use `console.log()` frequently to check your data
- Test each section independently
- Check the browser console for errors
- Validate your HTML structure

### Form Best Practices
- Always include `label` elements with `for` attributes
- Use appropriate `input` types for better UX
- Add `required` attribute for mandatory fields
- Test form validation by submitting

## Common Challenges & Solutions

### Challenge: "My template literals aren't working"
**Solution**: Make sure you're using backticks (`` ` ``) not regular quotes (`'` or `"`)

### Challenge: "I can't access my nested data"
**Solution**: Use dot notation step by step: `portfolio.owner.name`

### Challenge: "My for loop isn't working"
**Solution**: Check your array length: `for (let i = 0; i < array.length; i++)`

### Challenge: "Nothing appears on the page"
**Solution**: Check that your JavaScript files are loaded in the correct order

### Challenge: "My HTML looks broken"
**Solution**: Make sure to close all HTML tags in your template literals

## Extension Activities

If you finish early, try these enhancements:

### Advanced Data Analysis
```javascript
// Count technologies across all projects
let allTechs = [];
for (let i = 0; i < portfolio.projects.length; i++) {
    // Add logic to collect unique technologies
}
```

### Conditional Display
```javascript
// Only show featured projects
if (project.featured === true) {
    // Add featured star or special styling
}
```

### Multiple Portfolios
```javascript
// Create data for different personas
const profiles = [
    { name: "Designer", skills: ["UI/UX", "Figma"] },
    { name: "Developer", skills: ["JavaScript", "React"] }
];
```

## Next Steps (Future Weeks)

This data-driven foundation prepares you for:
- **Week 6**: Functions, array methods (`map`, `filter`), and your first interactive elements - JS Basics II and DOM & Events are one combined week this term
- **Week 7**: Rebuilding these same concepts as React components

## Resources

- [MDN: JavaScript Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
- [MDN: JavaScript Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
- [MDN: Template Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
- [MDN: HTML5 Input Types](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
