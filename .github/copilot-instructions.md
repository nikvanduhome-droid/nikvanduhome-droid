# Copilot Instructions for Home Portal

## Architecture Overview
This is a static client-side web application with no backend or build process. All functionality runs in the browser using vanilla HTML, CSS, and JavaScript.

- **Entry point**: `index.html` - Main portal with navigation and feature cards
- **Login flow**: `login.html` → `username.html` (redirects after successful auth)
- **User data**: Stored in `localStorage` (e.g., `loggedInUser` key)
- **Styling**: Centralized in `style.css` with reusable classes

## Key Patterns

### Authentication
User credentials are stored as GitHub Actions secrets and injected into `script.js` during deployment:
```javascript
const users = {
    '__USER1_USERNAME__': '__USER1_PASSWORD__',
    '__USER10_USERNAME__': '__USER10_PASSWORD__'
};
```
Login validation in `loginUser()` function checks against this object and sets `localStorage.loggedInUser`.

### UI Components
- **Buttons**: Use `.btn` class for consistent styling (green background, hover effects)
- **Cards**: Feature sections use `.card` class with grid layout in `.cards` container
- **Navigation**: Simple `<nav>` with anchor links, no client-side routing

### Demo Functionality
Placeholder demos use `demoAlert(feature)` from `script.js`:
```javascript
function demoAlert(feature) {
    alert(feature + " demo is currently under development.");
}
```
Called from `onclick` attributes in `index.html` cards.

### Styling Conventions
- Header: Dark background (`#1f2937`) with white text
- Hero section: Blue gradient background
- Cards: White background with subtle shadow
- Footer: Dark background matching header

## Development Workflow
- **Testing**: Open HTML files directly in browser (no server required)
- **Hosting**: Designed for GitHub Pages deployment
- **Debugging**: Use browser dev tools; check `localStorage` for user state
- **Modifications**: Edit HTML/JS/CSS directly; changes reflect immediately on refresh

## File Structure Reference
- `index.html`: Portal homepage with demo cards
- `login.html`: Authentication form
- `username.html`: Post-login user space (reads from localStorage)
- `script.js`: All JavaScript logic (login, demos)
- `style.css`: Complete styling system</content>
<parameter name="filePath">v:\nyx\Git\repos\Home\.github\copilot-instructions.md