# New_Star-frontend-
# Tailor Shop Website

A responsive multi-page website with PHP/MySQL backend for contact form management.

## Tech Stack

### Frontend
- **HTML5** - Semantic markup structure
- **CSS3** - Custom styling with responsive design
- **JavaScript (Vanilla)** - Mobile menu toggle functionality
- **Font Awesome 4.7.0** - Icon library (via CDN)
- **Google Maps Embed API** - Location integration

### Backend
- **PHP** - Server-side form processing
- **MySQL** - Database management
- **MySQLi** - Database connection interface

### Development Environment
- **XAMPP** (recommended) or any LAMP/WAMP stack
- PHP 7.0+
- MySQL 5.6+

## Project Structure

```
project-root/
│
├── index.html           # Main landing page
├── story.html           # About/History page
├── service.html         # Services showcase
├── facilities.html      # Facilities display
├── contact.html         # Contact form page
├── style.css            # Global stylesheet
│
├── formhandler.php      # Form processing logic
├── viewmessages.php     # Message retrieval & display
├── test.php             # PHP environment test
│
├── images/              # Image assets
└── README.md
```

## Technical Implementation

### HTML Features
- Responsive meta viewport configuration
- Multi-page navigation structure
- Semantic HTML5 elements
- Form validation attributes (`required`)
- External CDN integration
- Embedded iframe (Google Maps)

### CSS Architecture
```css
- Global reset styles
- Flexbox layouts
- CSS Grid (3-column responsive layouts)
- Media queries (@media)
  - Mobile: max-width: 480px
  - Tablet: max-width: 768px
- CSS transitions and hover effects
- Mobile-first navigation (hamburger menu)
```

### JavaScript Implementation
- DOM manipulation
- Event handling (onclick)
- CSS class toggling
- Mobile menu show/hide functionality

### PHP Backend

**formhandler.php**
- `$_SERVER["REQUEST_METHOD"]` validation
- MySQLi procedural connection
- `real_escape_string()` for SQL injection prevention
- POST data handling
- SQL INSERT operations
- Error handling with `connect_error`

**viewmessages.php**
- Database query execution
- `SELECT` with `ORDER BY DESC`
- `fetch_assoc()` loop for data retrieval
- HTML output generation

**Database Connection Parameters:**
```php
$servername = "localhost"
$username = "root"
$password = ""
$dbname = "tailorshop"
```

## Database Schema

```sql
CREATE TABLE contact_messages (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    mobno VARCHAR(20) NOT NULL,
    message TEXT NOT NULL,
    submitted_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Installation

### Prerequisites
```bash
- XAMPP/WAMP/LAMP
- Web browser
- Text editor (optional)
```

### Setup Steps

1. **Clone/Download repository**
```bash
git clone <repository-url>
```

2. **Move to server directory**
```bash
# Windows (XAMPP)
C:\xampp\htdocs\tailor-shop\

# Linux
/opt/lampp/htdocs/tailor-shop/

# macOS
/Applications/XAMPP/htdocs/tailor-shop/
```

3. **Create database**
```sql
CREATE DATABASE tailorshop;
USE tailorshop;

CREATE TABLE contact_messages (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    mobno VARCHAR(20) NOT NULL,
    message TEXT NOT NULL,
    submitted_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

4. **Configure database credentials** (if different from defaults)
Edit `formhandler.php` and `viewmessages.php`

5. **Test installation**
```
http://localhost/tailor-shop/test.php
http://localhost/tailor-shop/index.html
```

## API/External Services

- **Font Awesome CDN**: `https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css`
- **Google Maps Embed API**: Embedded iframe with specific coordinates

## Form Handling Flow

```
User fills form → POST to formhandler.php → 
Data sanitization → Database insertion → 
Success/Error response → Redirect option
```

## Responsive Breakpoints

- **Desktop**: Default (> 768px)
- **Tablet**: 768px and below
- **Mobile**: 480px and below

## CSS Techniques Used

- Linear gradients for backgrounds
- Box shadows
- Border radius
- Flexbox for layouts
- CSS Grid for service/facility cards
- Position absolute/relative
- Transform translate (centering)
- Transition effects
- Hover states
- Media queries

## JavaScript Functions

```javascript
showMenu()  // Display mobile navigation
hideMenu()  // Hide mobile navigation
```

## Security Considerations

**Current Implementation:**
- `real_escape_string()` for SQL injection prevention
- Form validation (HTML5 required attributes)
- Server-side request method checking

**Recommended Improvements:**
- Prepared statements with parameter binding
- CSRF token implementation
- Input sanitization and validation
- XSS prevention (htmlspecialchars)
- Rate limiting
- HTTPS in production
- Environment variables for credentials
- Authentication for admin pages

## Browser Compatibility

- Modern browsers (Chrome, Firefox, Safari, Edge)
- IE11+ (with potential CSS fallbacks needed)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Considerations

- External CDN for Font Awesome (caching)
- Image optimization recommended
- Minimal JavaScript (vanilla, no frameworks)
- Single CSS file (no preprocessors)

## License

MIT License

## Contributing

Pull requests welcome. For major changes, open an issue first.

---

**Stack**: HTML5 • CSS3 • JavaScript • PHP • MySQL
