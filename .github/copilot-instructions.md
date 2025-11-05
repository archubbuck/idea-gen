# GitHub Copilot Instructions for App Imagineer

## Project Overview
App Imagineer is a single-file React application for generating and managing app ideas. The entire application is contained in `index.html` and deployed to Firebase Hosting.

## Technology Stack
- **Frontend Framework:** React 18 (loaded via CDN)
- **UI Framework:** Tailwind CSS (loaded via CDN)
- **Styling:** Inter font family from Google Fonts
- **Backend:** Firebase (Authentication, Firestore)
- **State Management:** Zustand
- **Icons:** Lucide React
- **JSX Compilation:** Babel Standalone (browser-based compilation)
- **Hosting:** Firebase Hosting

## Architecture
- **Single-File Application:** All JavaScript, JSX, and styles are contained within `index.html`
- **No Build Process:** The application runs directly in the browser using Babel for JSX compilation
- **CDN Dependencies:** All libraries are loaded from CDNs, no npm dependencies

## File Structure
```
/
├── index.html          # Complete React application
├── firebase.json       # Firebase Hosting configuration
└── README.md          # Deployment instructions
```

## Coding Standards

### HTML/JSX
- Use semantic HTML elements
- Keep JSX within the `<script type="text/babel">` tag in index.html
- Use React 18 hooks (useState, useEffect, useCallback, useMemo, useRef)
- Follow functional component patterns

### Styling
- Use Tailwind CSS utility classes for all styling
- Maintain responsive design with mobile-first approach
- Use Inter font family consistently
- Keep custom CSS minimal and limited to animations or special effects

### JavaScript
- Use ES6+ modern JavaScript syntax
- Destructure globals from React, Firebase, and other libraries
- Use const/let instead of var
- Use arrow functions for callbacks
- Keep functions small and focused

### Firebase
- Firebase configuration is loaded from environment variables
- Use Firebase Authentication for user management
- Use Firestore for data storage
- Follow Firebase best practices for security rules

### State Management
- Use Zustand for global state management
- Use React hooks for local component state
- Keep state as close to where it's used as possible

## Development Workflow

### Making Changes
1. Edit `index.html` directly
2. Test locally by opening the file in a browser or using a local web server
3. Verify Firebase integration works correctly
4. Deploy to Firebase Hosting for production

### Testing
- Since there is no automated test suite, manually test all changes:
  - Test user authentication flows
  - Test Firestore read/write operations
  - Test all UI interactions
  - Test responsive design on different screen sizes
  - Test in multiple browsers (Chrome, Firefox, Safari)

### Deployment
```bash
# Deploy to Firebase Hosting
firebase deploy --only hosting
```

## Important Constraints

### Single-File Architecture
- **DO NOT** split the application into multiple files
- **DO NOT** introduce a build process or bundler
- **DO NOT** add npm dependencies
- All code must remain in `index.html`

### Dependencies
- **DO NOT** add new npm packages
- Use only CDN-available libraries
- Verify CDN URLs are correct and use specific version numbers
- Prefer stable, well-maintained libraries

### Firebase Configuration
- Keep Firebase configuration secure
- Use environment variables for sensitive config
- Do not hardcode API keys or credentials

## Common Tasks

### Adding a New Component
- Define components as functional components within the script tag
- Use React hooks for state and effects
- Apply Tailwind classes for styling
- Ensure components are responsive

### Adding a New Page/Route
- The application uses client-side routing
- Add route handling in the main routing logic
- Update navigation components as needed

### Modifying Firebase Integration
- Follow Firebase SDK documentation for the version being used (10.12.2)
- Test authentication and database operations thoroughly
- Consider offline capabilities and error handling

### UI Updates
- Use existing Tailwind classes first
- Add custom CSS only when Tailwind utilities are insufficient
- Maintain consistency with existing design patterns
- Test animations and transitions

## Error Handling
- Implement try-catch blocks for async operations
- Provide user-friendly error messages
- Log errors to console for debugging
- Handle Firebase authentication and network errors gracefully

## Security Considerations
- Validate user input
- Use Firebase Security Rules to protect data
- Implement proper authentication checks
- Sanitize user-generated content
- Follow OWASP security best practices

## Pull Request Guidelines
- Test all changes locally before committing
- Verify the application works after deployment
- Document any new features or significant changes
- Keep commits focused and atomic
- Update README.md if deployment process changes

## Documentation
- Comment complex logic or non-obvious code
- Use JSDoc style comments for functions where helpful
- Keep comments concise and relevant
- Update this file when adding new conventions or practices

## Best Practices
- Keep the single-file architecture intact
- Prioritize code readability and maintainability
- Use modern React patterns (hooks, functional components)
- Optimize for performance (lazy loading, memoization)
- Ensure accessibility (semantic HTML, ARIA labels when needed)
- Maintain backward compatibility with existing Firebase data
