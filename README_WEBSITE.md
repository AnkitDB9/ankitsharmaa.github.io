# Ankit Sharma - Personal Website

A beautiful, LinkedIn-inspired personal website built with HTML, CSS, and JavaScript. Features a modern blue and white design, responsive layout, blog section for data engineering content, and a functional contact form.

## 🌟 Features

- **LinkedIn-inspired Design**: Clean, professional blue and white theme
- **Responsive Layout**: Works perfectly on desktop, tablet, and mobile devices
- **Interactive Navigation**: Smooth scrolling and active section highlighting
- **Hero Section**: Eye-catching introduction with profile card
- **About Section**: Skills showcase and experience timeline
- **Blog Section**: Ready for data engineering articles and tutorials
- **Contact Form**: Functional contact form with email integration
- **Animations**: Smooth scroll animations and typing effects
- **Modern UI**: Professional design with hover effects and transitions

## 📁 Project Structure

```
├── index.html          # Main HTML file
├── styles.css          # CSS styles with LinkedIn-inspired theme
├── script.js           # JavaScript for interactivity
├── email-config.md     # Email service setup guide
└── README_WEBSITE.md   # This file
```

## 🚀 Quick Start

1. **Clone or download** the project files
2. **Open `index.html`** in your web browser to preview locally
3. **Customize the content** with your information
4. **Set up email service** (see Email Configuration section)
5. **Deploy to your preferred hosting platform**

## ✏️ Customization

### Personal Information
Edit `index.html` to update:
- Name and title in navigation and hero section
- Professional summary and skills
- Experience details
- Contact information
- Social media links

### Blog Content
Replace the sample blog posts in the blog section with your actual articles:
```html
<article class="blog-card">
    <div class="blog-content">
        <h3>Your Blog Post Title</h3>
        <p>Your blog post excerpt...</p>
        <div class="blog-meta">
            <span class="blog-date">Publication Date</span>
            <span class="blog-read-time">Read Time</span>
        </div>
        <a href="your-post-url" class="blog-link">Read More</a>
    </div>
</article>
```

### Styling
Modify `styles.css` to:
- Change color scheme (currently uses LinkedIn blue #0077b5)
- Adjust fonts and spacing
- Customize animations and effects

## 📧 Email Configuration

The contact form requires email service setup. See `email-config.md` for detailed instructions on:

- **EmailJS** (Recommended - Free and easy)
- **Netlify Forms** (If deploying on Netlify)
- **Formspree** (Alternative service)

## 🌐 Deployment Options

### GitHub Pages (Recommended for ankitsharma.org)

1. **Create a new repository** on GitHub
2. **Upload all files** to the repository
3. **Go to Settings > Pages**
4. **Select source**: Deploy from a branch (main)
5. **Custom domain**: Add `ankitsharma.org` in the custom domain field
6. **DNS Configuration**: Point your domain to GitHub Pages:
   ```
   A Records:
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   
   CNAME Record:
   www -> your-username.github.io
   ```

### Netlify

1. **Drag and drop** your project folder to [Netlify](https://netlify.com)
2. **Configure custom domain** in site settings
3. **Enable Netlify Forms** if using that option for contact form

### Vercel

1. **Import project** from GitHub to [Vercel](https://vercel.com)
2. **Configure custom domain** in project settings
3. **Deploy automatically** on every push

## 🛠️ Development

### Local Development
- Simply open `index.html` in your browser
- Use Live Server extension in VS Code for auto-refresh
- Test responsiveness using browser dev tools

### Adding Blog Posts
For a full blog implementation, consider:
- Static site generators (Jekyll, Hugo, Gatsby)
- Headless CMS (Contentful, Strapi)
- Markdown-based solutions

## 📱 Browser Support

- Chrome (recommended)
- Firefox
- Safari
- Edge
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🎨 Design Credits

- **Color Scheme**: Inspired by LinkedIn's professional blue palette
- **Typography**: Inter font family for modern readability
- **Icons**: Font Awesome for consistent iconography
- **Layout**: CSS Grid and Flexbox for responsive design

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Feel free to fork this project and customize it for your own use. If you make improvements that could benefit others, pull requests are welcome!

## 📞 Support

If you need help customizing or deploying this website, feel free to reach out through the contact form on the live site.

---

**Built with ❤️ for the data engineering community**
