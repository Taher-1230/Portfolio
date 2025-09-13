# Dynamic Portfolio Website 🚀

A highly dynamic, single-page portfolio website featuring cool tech animations, theme toggle functionality, and modern responsive design.

## ✨ Features

- **🎨 Dynamic Theme Toggle**: Switch between light and dark modes with smooth transitions
- **🔥 Cool Tech Animations**: 
  - Floating background elements
  - Rotating tech orbit with animated icons
  - Skill progress bars with smooth fill animations
  - Counter animations for statistics
  - Parallax scrolling effects
- **📱 Fully Responsive**: Optimized for all devices and screen sizes
- **🎯 Single Page Application**: Smooth scrolling navigation between sections
- **💫 Interactive Elements**:
  - Button ripple effects
  - Hover animations on all interactive elements
  - Form validation with notifications
  - Easter egg (try the Konami code: ↑↑↓↓←→←→BA)
- **⚡ Performance Optimized**: 
  - Throttled scroll events
  - Intersection Observer API for animations
  - CSS animations using GPU acceleration

## 🛠️ Tech Stack

- **HTML5**: Semantic markup structure
- **CSS3**: Modern styling with CSS Grid, Flexbox, and CSS Variables
- **Vanilla JavaScript**: Pure JS with modern ES6+ features
- **Google Fonts**: Inter font family for typography

## 🏗️ Project Structure

```
portfolio-website/
├── index.html              # Main HTML file
├── css/
│   └── styles.css          # Main stylesheet with animations
├── js/
│   └── script.js           # Interactive JavaScript functionality
├── assets/                 # Static assets (images, etc.)
├── package.json            # Node.js dependencies and scripts
└── README.md              # Project documentation
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)

### Installation

1. **Clone or navigate to the project directory**:
   ```bash
   cd portfolio-website
   ```

2. **Install dependencies** (optional, for development tools):
   ```bash
   npm install
   ```

3. **Open the website**:
   - **Simple**: Just open `index.html` in your web browser
   - **Development server**: Run `npm run dev` to start a live server
   - **HTTP server**: Run `npm run serve` for a basic HTTP server

### Development Scripts

- `npm run dev` - Start live development server on port 3000
- `npm run serve` - Start HTTP server on port 8080
- `npm run build` - Minify CSS and JavaScript files
- `npm run lint` - Run ESLint on JavaScript files
- `npm run format` - Format code with Prettier
- `npm run validate` - Validate HTML markup

## 🎨 Customization

### Personalizing the Content

1. **Update Personal Information**:
   - Edit the name, title, and description in `index.html`
   - Replace placeholder contact information
   - Add your own project descriptions and links

2. **Theme Colors**:
   - Modify CSS variables in `css/styles.css` under `:root` and `[data-theme="dark"]`
   - Change `--accent-primary`, `--accent-secondary`, and gradient colors

3. **Animations**:
   - Adjust animation durations in CSS
   - Modify floating element positions and timing
   - Customize orbit speeds and sizes

4. **Content Sections**:
   - Add or remove sections as needed
   - Update navigation links accordingly
   - Modify the project grid and skill categories

### Adding Your Projects

Replace the placeholder projects in the Projects section:

```html
<div class="project-card">
    <div class="project-image">
        <!-- Add your project screenshot here -->
        <div class="project-overlay">
            <button class="btn btn-primary">View Project</button>
        </div>
    </div>
    <div class="project-content">
        <h3>Your Project Name</h3>
        <p>Your project description</p>
        <div class="project-tags">
            <span>Technology</span>
            <span>Used</span>
        </div>
    </div>
</div>
```

## 🌟 Key Features Explained

### Theme Toggle
- Automatically saves user preference to localStorage
- Smooth color transitions between themes
- Uses CSS custom properties for easy theme management

### Animations
- **Intersection Observer**: Triggers animations when elements come into view
- **CSS Transforms**: Hardware-accelerated animations for smooth performance
- **Throttled Scroll Events**: Optimized scroll handling for 60fps performance

### Responsive Design
- Mobile-first approach with progressive enhancement
- CSS Grid and Flexbox for flexible layouts
- Hamburger menu for mobile navigation

## 🐛 Browser Support

- Chrome 88+
- Firefox 85+
- Safari 14+
- Edge 88+

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Feel free to fork this project and customize it for your own portfolio! If you make improvements that could benefit others, pull requests are welcome.

## 📞 Contact

- **Email**: your.email@example.com
- **LinkedIn**: [Your LinkedIn Profile](https://linkedin.com/in/yourprofile)
- **GitHub**: [Your GitHub Profile](https://github.com/yourusername)

---

**Enjoy building your dynamic portfolio! 🎉**

> **Tip**: Try the Konami code (↑↑↓↓←→←→BA) for a fun easter egg! 🎮