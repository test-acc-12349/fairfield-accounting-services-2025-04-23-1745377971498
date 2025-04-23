# Fairfield Landing Page Maintenance Guide

This guide will help you maintain and customize the Fairfield accounting services landing page. Whether you're new to web development or need a quick reference, follow these instructions to make common updates safely and effectively.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains your company name and navigation menu. To update:

1. **Company Name:**
```html
<!-- Find this line in the header -->
<div class="text-2xl font-bold text-gray-800">Fairfield</div>
```
Simply replace "Fairfield" with your company name. The `text-2xl` class controls size, and `text-gray-800` controls color.

2. **Navigation Menu Items:**
```html
<div class="hidden md:flex space-x-8">
    <a href="#services" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">Services</a>
    <!-- More menu items -->
</div>
```
To modify menu items:
- Change the text between `<a>` tags
- Keep the `href` attributes matching your section IDs
- Maintain the `class` attributes for consistent styling

### Hero Section
Located at the top of the page with the main headline:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-8">
    We count what counts for your business
</h1>
```
- Replace the headline text while keeping the classes
- The responsive text sizes (`text-4xl`, `md:text-5xl`, `lg:text-6xl`) ensure proper display on all devices

### Services Cards
Each service card follows this structure:
```html
<div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1">
    <!-- Icon container -->
    <div class="w-12 h-12 bg-indigo-100 rounded-full flex items-center justify-center mb-6">
        <!-- SVG icon here -->
    </div>
    <h3 class="text-xl font-semibold text-gray-900 mb-4">Service Title</h3>
    <p class="text-gray-600 leading-relaxed">Service description goes here.</p>
</div>
```
To update:
1. Change the title in the `<h3>` tag
2. Modify the description in the `<p>` tag
3. Keep all classes to maintain styling and hover effects

## Managing Links

### Navigation Links
Current navigation links are:
```html
<a href="#services">Services</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
<a href="#contact">Contact</a>
```
To update:
1. Ensure section IDs match your href values
2. For external links, use complete URLs: `href="https://example.com"`
3. For internal pages, use relative paths: `href="about.html"`

### Call-to-Action Buttons
The main CTA buttons currently point to a placeholder URL:
```html
<a href="https://theaccountants.com" class="px-8 py-4 bg-indigo-600 text-white rounded-full">
```
Replace `https://theaccountants.com` with your actual URL for:
- "Get Started" button in header
- "Start Your Journey" button in hero section
- "Get Started Today" button in final CTA section

## Adding Privacy and Terms Pages

### Footer Links Setup
Locate the legal section in the footer:
```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2 text-gray-400">
        <li><a href="#" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To link privacy and terms pages:
1. Create two new files:
   - `privacy.html`
   - `terms.html`

2. Update the href attributes:
```html
<li><a href="privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

Common issues and solutions:

### Broken Styles
If styles aren't applying:
1. Check Tailwind CDN link in header:
```html
<script src="https://cdn.tailwindcss.com"></script>
```
2. Verify class names match exactly (Tailwind is case-sensitive)
3. Ensure no spaces in class names

### Animation Issues
If animations aren't working:
1. Verify AOS script and CSS are loaded:
```html
<link href="https://unpkg.com/aos@next/dist/aos.css" rel="stylesheet">
<script src="https://unpkg.com/aos@next/dist/aos.js"></script>
```
2. Check `data-aos` attributes on elements
3. Confirm AOS initialization:
```html
<script>
    AOS.init({
        duration: 1000,
        once: true
    });
</script>
```

### Responsive Design
If layout breaks on mobile:
1. Keep the `md:` prefixed classes for responsive behavior
2. Maintain the mobile menu button in header
3. Don't remove the `container` and `mx-auto` classes from section wrappers

Remember to test all changes across different devices and browsers before publishing updates.