# Website Development

## Overview

The conference website serves as the primary information hub and first impression for potential attendees. Modern useR! conferences leverage git-based workflows and static site generators for maintainable, collaborative website development. This guide details the process used for useR! 2025, which can be replicated for future conferences.

## Technology Stack

### Core Technologies

**Static Site Generator**: Quarto
- Modern, R-friendly framework
- Supports markdown, R, Python, Julia
- Built-in support for academic content
- Excellent documentation and community

**Version Control**: Git with GitLab
- Repository: https://gitlab.com/rconf/user-2025-website
- Collaborative development
- Version history and rollback capability
- Issue tracking for website tasks
- Merge request workflow for reviews

**Deployment**: Netlify
- Continuous deployment from git
- Automatic HTTPS
- Preview deployments for branches
- Form handling capabilities
- Global CDN for fast loading

**Domain**: useR2025.r-project.org
- Production site deployed automatically from main branch
- Branch deployments: `branch--sitename.netlify.app`
- Merge request previews: `deploy-preview-#--sitename.netlify.app`
- Provided through R Consortium

## Getting Started: Clone and Adapt

### Why Clone Instead of Starting Fresh

**Benefits**:
- Proven structure and design
- Pre-built components (countdown timer, speaker cards, schedule)
- Responsive design already tested
- SEO optimization in place
- Accessibility features included

**Sources to Clone From**:
- Previous useR! conference sites
- satRdays Quarto template (used for useR! 2025)
- R Consortium conference templates

### Initial Setup Process

```bash
# Clone the template repository (useR! 2025 used satRdays template)
git clone https://gitlab.com/rconf/satrdays-template user-2025-website

# Navigate to the directory
cd user-2025-website

# Remove original git history
rm -rf .git

# Initialize new repository
git init
git add .
git commit -m "Initial commit from satRdays template"

# Create new remote repository on GitLab
# Add remote and push
git remote add origin https://gitlab.com/rconf/user-2025-website
git push -u origin main
```

### Key Modifications from Template

**From useR! 2025 git history**:
1. Update for useR 2025 (initial customization)
2. Rename project files
3. Update copyright information
4. Replace satRdays references with useR
5. Fix keydates formatting
6. Add "in progress" banner for early launch
7. Replace placeholder content
8. Visual editor edits for content

## Site Structure

### Directory Organization

```
user-2025-website/
├── _quarto.yml           # Main configuration
├── index.qmd             # Homepage
├── about/
│   ├── about.qmd        # About the conference
│   ├── organizers.qmd   # Committee information
│   └── sponsors/        # Sponsor listings
├── participation/
│   ├── call.qmd         # Call for abstracts
│   ├── coc.qmd          # Code of conduct
│   └── keydates/        # Important dates
├── program/
│   ├── schedule/        # Conference schedule
│   └── speakers/        # Speaker profiles
├── register.qmd         # Registration information
├── contact.qmd          # Contact details
├── img/                 # Images and graphics
├── css/                 # Custom styling
├── js/                  # JavaScript (countdown, etc.)
└── _site/              # Generated site (do not edit)
```

### Configuration File (_quarto.yml)

Key settings to customize:

```yaml
project:
  type: website
  
website:
  title: "useR! [YEAR]"
  description: "International R User Conference"
  site-url: "https://user[YEAR].r-project.org"
  
  navbar:
    logo: img/user-conf.png
    items:
      - text: "About"
      - text: "Program"
      - text: "Register"
      - text: "Sponsors"
      
  footer:
    content: "© 2025 useR! Conference"
    
format:
  html:
    theme: 
      - cosmo
      - css/styles.scss
```

## Content Management

### Dynamic Content with Data Files

**Speakers (speakers.yml)**:
```yaml
speakers:
  - name: "Jane Doe"
    affiliation: "University X"
    title: "Opening Keynote"
    bio: "Distinguished professor..."
    image: "img/speakers/jane-doe.jpg"
    
  - name: "John Smith"
    affiliation: "Company Y"
    title: "Closing Keynote"
    bio: "Chief Data Scientist..."
    image: "img/speakers/john-smith.jpg"
```

**Schedule (schedule.yml)**:
```yaml
day1:
  date: "2025-08-08"
  sessions:
    - time: "08:00"
      title: "Registration"
      type: "break"
    - time: "09:00"
      title: "Opening Keynote"
      speaker: "Jane Doe"
      room: "Penn 1"
```

**Sponsors (sponsors.yml)**:
```yaml
platinum:
  - name: "R Consortium"
    logo: "img/sponsors/r-consortium.png"
    url: "https://r-consortium.org"
    
gold:
  - name: "Posit"
    logo: "img/sponsors/posit.png"
    url: "https://posit.co"
```

### Template Components

**Countdown Timer**:
- JavaScript countdown to conference start
- Updates automatically
- Customizable styling
- Mobile responsive

**Speaker Cards**:
- Automated generation from YAML
- Consistent formatting
- Image optimization
- Social media links

**Schedule Display**:
- Tabbed view by day
- Room assignments
- Color coding by session type
- Print-friendly version

## Development Workflow

### Local Development

```bash
# Install Quarto (if not installed)
# https://quarto.org/docs/get-started/

# Start development server (as per useR! 2025 README)
quarto preview

# Build site (typically handled by Netlify automatically)
quarto render

# Note: Avoid executable cells in .qmd files
# Can preview in RStudio or VS Code with Quarto extension
```

### Git Workflow

**Branch Strategy**:
- `main`: Production website
- `develop`: Staging changes
- Feature branches for specific updates

**Commit Messages**:
```
Add: New speaker profiles
Update: Registration deadlines
Fix: Mobile navigation issue
Refactor: Sponsor page layout
```

### Collaborative Editing

**For Technical Team**:
1. Fork repository on GitLab
2. Clone your fork locally
3. Make changes
4. Push to your fork
5. Create merge request to main repository
6. Review and merge

**For Non-Technical Contributors**:
1. Open an issue for website mistakes
2. Or use GitLab web editor
3. Edit markdown files directly
4. Submit merge request for review

**Contribution Guidelines (useR! 2025)**:
- For mistakes: Open an issue
- For changes: Fork, modify, create merge request
- Avoid executable cells in .qmd files

## Deployment with Netlify

### Initial Setup

1. **Create Netlify Account**
   - Sign up at netlify.com
   - Connect GitLab/GitHub account

2. **Import Project**
   - New site from Git
   - Select repository
   - Configure build settings

3. **Build Settings**:
   ```
   Build command: quarto render
   Publish directory: _site
   ```

4. **Environment Variables** (if needed):
   - API keys for forms
   - Analytics IDs
   - Feature flags

### Continuous Deployment

**Automatic Deployments (useR! 2025 configuration)**:
- Main branch → useR2025.r-project.org (production)
- Branch deployments → `branch--sitename.netlify.app`
- Merge request previews → `deploy-preview-#--sitename.netlify.app`
- Rendering handled automatically by Netlify

**Deploy Previews**:
- Unique URL for each merge request
- Share with reviewers before merging
- Automatic cleanup after merge

### Domain Configuration

**Setting up useR[YEAR].r-project.org**:

1. **Obtain Domain Access**
   - Contact R Consortium for subdomain
   - Receive DNS configuration details

2. **Configure in Netlify**:
   - Add custom domain
   - Configure DNS records
   - Enable HTTPS

3. **DNS Records**:
   ```
   Type: CNAME
   Name: user2025
   Value: [netlify-site].netlify.app
   ```

## Content Guidelines

### Writing for the Web

**Best Practices**:
- Clear, concise headings
- Short paragraphs (3-4 sentences)
- Bulleted lists for scanning
- Call-to-action buttons
- Mobile-first thinking

### SEO Optimization

**Meta Tags**:
```yaml
title: "useR! 2025 - International R Conference"
description: "Join us for useR! 2025 in Durham, NC..."
image: "img/conference-banner.jpg"
```

**Structured Data**:
- Event schema markup
- Speaker profiles
- Schedule information

### Accessibility

**Requirements**:
- Alt text for all images
- Proper heading hierarchy
- Sufficient color contrast
- Keyboard navigation
- Screen reader testing

## Maintenance Timeline

### 12 Months Before
- Clone and customize template
- Set up repository and deployment
- Launch basic site with save-the-date

### 9 Months Before
- Add call for abstracts
- Open sponsorship information
- Enable registration details

### 6 Months Before
- Publish accepted speakers
- Release preliminary schedule
- Add travel information

### 3 Months Before
- Finalize schedule
- Add session details
- Update logistics information

### 1 Month Before
- Final speaker updates
- Last-minute announcements
- Technical program details

### During Conference
- Live updates
- Session changes
- Social media integration

### After Conference
- Post presentations/recordings
- Thank you messages
- Archive for future reference

## Common Issues and Solutions

### Build Failures

**Problem**: Site won't build on Netlify
**Solution**: 
- Check Quarto version compatibility
- Verify all file paths are correct
- Review build logs for specific errors

### Broken Links

**Problem**: Internal links not working
**Solution**:
- Use relative paths
- Check for renamed files
- Test with link checker tool

### Slow Performance

**Problem**: Site loads slowly
**Solution**:
- Optimize images (WebP format)
- Minimize JavaScript
- Enable Netlify optimizations
- Use CDN for large files

## Security Considerations

### Form Handling

- Use Netlify Forms or similar service
- Implement CAPTCHA for spam prevention
- Never store sensitive data in git
- Use environment variables for API keys

### Content Security

- Regular dependency updates
- HTTPS enforcement
- Content Security Policy headers
- Regular security audits

## Handoff Documentation

### For Next Year's Organizers

**Provide**:
- Repository access
- Deployment credentials
- Documentation of customizations
- List of known issues
- Contact for questions

**Archive**:
- Final version of site
- Analytics data
- User feedback
- Lessons learned

## Website Development Checklist

### Initial Setup
- [ ] Clone template repository
- [ ] Customize configuration
- [ ] Set up GitLab/GitHub repository
- [ ] Configure Netlify deployment
- [ ] Set up custom domain

### Content Development
- [ ] Create homepage content
- [ ] Add committee information
- [ ] Write call for abstracts
- [ ] Develop sponsor packages
- [ ] Create registration page

### Pre-Launch
- [ ] Test all links
- [ ] Verify mobile responsiveness
- [ ] Check accessibility
- [ ] Set up analytics
- [ ] Create 404 page

### Maintenance
- [ ] Regular content updates
- [ ] Monitor performance
- [ ] Respond to issues
- [ ] Backup content
- [ ] Document changes

## Next Steps

With website infrastructure in place, proceed to:
- [Registration & Payment](04-registration-payment.md) - Setting up attendee management
- [Program Planning](06-program-planning.md) - Developing conference content
- [Sponsorship](05-sponsorship.md) - Promoting sponsorship opportunities online
---

**Navigation**: [← Venue & Logistics](02-venue-logistics.md) | [Registration & Payment →](04-registration-payment.md)
