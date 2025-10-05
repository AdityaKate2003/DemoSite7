# CityCare Hospital Website

## Overview

CityCare Hospital is a modern, professional hospital website built as a static multi-page application. The site serves as an online presence for a healthcare facility, providing information about medical services, departments, doctors, and enabling patients to book appointments. The website is built using vanilla HTML, CSS, and JavaScript without any frameworks, focusing on clean design, smooth animations, and responsive layouts.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Static Multi-Page Application (MPA)**
- The application uses traditional HTML pages with client-side JavaScript for interactivity
- Each page (home, about, departments, doctors, contact) is a separate HTML file
- Navigation is handled through standard anchor links between pages
- Rationale: Simple hosting requirements, fast initial load times, SEO-friendly structure
- Trade-off: Some code duplication across pages vs. single-page application benefits

**CSS Architecture**
- Single centralized stylesheet (`style.css`) shared across all pages
- CSS custom properties (variables) for consistent theming and easy maintenance
- Mobile-first responsive design approach
- Rationale: Maintains design consistency, reduces HTTP requests, easier theme management
- Design system includes predefined color palette, shadows, and spacing values

**JavaScript Interaction Model**
- Vanilla JavaScript with event-driven architecture (`main.js`)
- Intersection Observer API for scroll-based animations and lazy loading effects
- DOM manipulation for dynamic content (mobile navigation, counters, modals)
- Rationale: No framework overhead, faster load times, simpler deployment
- Trade-off: Manual DOM management vs. framework abstractions

### Design Patterns & Features

**Animation System**
- Fade-in animations triggered by scroll position using Intersection Observer
- CSS transitions for hover effects and state changes
- Counter animations for statistics display
- Rationale: Enhances user engagement without impacting performance

**Responsive Navigation**
- Sticky header that remains visible during scroll
- Mobile hamburger menu with toggle functionality
- Active page indicator in navigation
- Rationale: Improves mobile usability and provides consistent navigation experience

**Component-Based Structure**
- Reusable UI patterns: hero sections, cards, modals, forms
- Consistent styling through CSS classes
- Rationale: Maintains visual consistency while allowing per-page customization

**Form Handling**
- Client-side form validation for appointment booking
- Success message display after form submission
- Rationale: Immediate user feedback, reduced server load for validation

### File Structure

```
/
├── index.html          # Home page (hero, stats, services overview)
├── about.html          # Hospital story, mission, values
├── departments.html    # Medical services and specializations
├── doctors.html        # Team profiles with filtering
├── contact.html        # Appointment booking form and contact info
├── style.css           # Global styles and theme definitions
├── main.js             # Shared JavaScript functionality
└── attached_assets/    # Project documentation and assets
```

## External Dependencies

### Third-Party Libraries

**Font Awesome (CDN)**
- Version: 6.4.0
- Purpose: Icon library for UI elements (navigation, department icons, form fields)
- Integration: Loaded via CDN link in HTML head
- Usage: Provides consistent, scalable icons throughout the application

**Google Fonts**
- Font: Poppins (weights: 300, 400, 500, 600, 700)
- Purpose: Primary typography for modern, clean aesthetic
- Integration: Imported via CSS `@import` statement
- Rationale: Improves readability and provides professional appearance

### Browser APIs

**Intersection Observer API**
- Purpose: Efficient scroll-based animations and visibility detection
- Usage: Triggers fade-in animations when elements enter viewport
- Fallback: Graceful degradation for older browsers (elements remain visible)

**Form API**
- Purpose: Native HTML5 form validation and submission
- Usage: Client-side validation for appointment booking form
- Note: Backend integration would be required for actual appointment processing

### Future Integration Points

**Backend Consideration**
- Form submissions currently handled client-side only
- Future implementation would require server-side endpoint for appointment processing
- Email notification system would need integration with email service provider
- Database storage would be needed for appointment records

**Potential Services**
- Email service (SendGrid, Mailgun, or SMTP server) for appointment confirmations
- Calendar API integration for appointment scheduling
- Analytics platform (Google Analytics) for user behavior tracking
- Content Management System (CMS) for easier content updates by non-technical staff