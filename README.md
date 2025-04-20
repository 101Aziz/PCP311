# Ontario PCP Paramedic Student Blog Website

This repository contains a static website for a paramedic student's personal blog documenting their 42-day journey through the Patient Care Skills portion of their Ontario PCP program. The site contains daily summaries of what the student has learned, with appropriate disclaimers that this content represents personal notes, not official materials.

## Structure

- `index.html` - The main HTML file containing the structure of the website, styles, and JavaScript
- `README.md` - This file with instructions

## Deployment Instructions

### Setting up with Netlify

1. **Create a GitHub repository**
   - Create a new repository on GitHub
   - Upload the `index.html` file to your repository

2. **Sign up for Netlify**
   - Go to [Netlify](https://www.netlify.com/) and sign up for a free account
   - Connect your GitHub account to Netlify

3. **Deploy your site**
   - From the Netlify dashboard, click "New site from Git"
   - Select GitHub as your Git provider
   - Select your repository
   - In the basic build settings:
     - Build command: Leave blank (not needed for simple static sites)
     - Publish directory: Leave as root directory "/"
   - Click "Deploy site"

4. **Set up your custom domain (optional)**
   - In the Netlify dashboard, go to "Domain settings"
   - Click "Add custom domain" and follow the instructions

### How to Update the Website

#### Adding New Day Content

1. Open the `index.html` file
2. Find the `getDayTitle` function in the JavaScript section
3. Add a new entry for the day number and its title:
   ```javascript
   const titles = {
       3: "Airway Management",
       4: "Patient Assessment",
       5: "Trauma Management",
       // Add your new day here
       6: "Your New Title"
   };
   ```

4. Find the `getDayContent` function
5. Add a new condition for your day with the HTML content:
   ```javascript
   if (day === 3) {
       // Existing Day 3 content
   } else if (day === 6) { // Your new day number
       return `
           <h3>Your Day Title</h3>
           <p>Introduction paragraph for your day's content</p>
           
           <div class="key-point">
               <h4>1. First Key Point</h4>
               <ul>
                   <li>First bullet point</li>
                   <li>Second bullet point</li>
               </ul>
           </div>
           
           <div class="key-point">
               <h4>2. Second Key Point</h4>
               <ul>
                   <li>First bullet point</li>
                   <li>Second bullet point</li>
               </ul>
           </div>
           
           <!-- Add more key points as needed -->
       `;
   } else {
       // Default "coming soon" message
   }
   ```

6. Update the `currentDay` variable to reflect the latest day you've added:
   ```javascript
   const currentDay = 6; // Change this to your new day number
   ```

7. Commit and push your changes to GitHub
8. Netlify will automatically rebuild and deploy your site

#### Content Structure for Each Day

Follow this template for adding new day content:

```html
<h3>Day Title</h3>
<p>My Personal Notes – Day X of PCP Skills Training</p>
<div style="background-color: #fff3cd; border-left: 4px solid #ffc107; padding: 0.5rem; margin-bottom: 1rem; font-size: 0.9rem;">
    <strong>Note:</strong> These are my personal learning notes and may not be complete or error-free. Always verify with official sources.
</div>

<div class="key-point">
    <h4>1. Key Point Title</h4>
    <ul>
        <li>First bullet point</li>
        <li>Second bullet point</li>
    </ul>
</div>

<!-- Add more key points as needed -->
```

## Tips for Managing Your Site

1. **Local testing**: Before pushing changes, open the HTML file in your browser to check that everything looks good

2. **Version control**: Keep track of your changes by making meaningful commit messages

3. **Backup**: Keep a local copy of your site in case you need to restore it

4. **Images**: If you want to add images, create an "images" folder in your repository and reference them using relative paths

5. **CSS customization**: You can modify the CSS in the `<style>` section to customize the look and feel

6. **Mobile testing**: Use browser developer tools to test how your site looks on mobile devices

## Advanced Customization

If you want to expand your site in the future, consider:

1. **Separating files**: Move CSS and JavaScript to separate files
2. **Adding search functionality**: Implement a search feature for finding content across days
3. **User authentication**: Add login functionality if you want to restrict access
4. **Interactive elements**: Add quizzes or interactive scenarios
5. **PDF downloads**: Create PDF versions of each day's content for offline study

For any questions or issues, please refer to the [Netlify documentation](https://docs.netlify.com/).
