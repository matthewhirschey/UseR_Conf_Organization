# Registration & Payment Systems

## Overview

A robust registration and payment system is essential for managing attendees, collecting fees, and gathering critical information for conference planning. Modern useR! conferences have used Indico for registration management and Stripe for payment processing.

## Platform Selection: Indico

### Why Indico

Indico is a platform for academic conferences, providing registration, abstract submission, and conference management in one integrated system. Used by CERN and major universities worldwide, it accommodates scientific conferences like useR.

**Key Benefits for useR!**:
- All-in-one solution: registration, abstracts, scheduling, payments
- Academic-friendly features and workflows
- Open source and actively maintained
- GDPR compliant with strong privacy controls
- Proven track record with large conferences

### Indico Interface Overview

**Main Conference Modules** (as used in useR! 2025):
- **Call for Abstracts** - Manage submission and review process
- **Registration** - Handle attendee registration and payments
- **Timetable** - Build and display conference schedule
- **Contribution Management** - Track talks, posters, workshops

### Quick Setup Guide

**Getting Started**:
1. Request Indico instance (university or hosted)
2. Create your conference event
3. Configure basic settings (dates, location, contact)
4. Enable needed modules (registration, abstracts, etc.)
5. Customize forms and workflows
6. Test with a small group before launch

## Payment Processing with Stripe

### Setting Up Payments in Indico

The base installation of Indico doens't have Stripe integrations built-in. But a plug-in is available that can be installed on your version of Indico. After doing this, then connect Stripe. 

**Quick Setup**:
1. Create Stripe account
2. Get API keys from Stripe dashboard
3. In Indico: Settings → Payment → Add Stripe
4. Enter your Stripe keys
5. Configure currency and payment methods
6. Test with Stripe test mode first

### Payment Configuration

**What Indico Handles Automatically**:
- Secure payment form
- PCI compliance
- Receipt generation
- Refund processing
- Payment status tracking
- Invoice creation

## Registration Structure

### Pricing Tiers

**From useR! 2025**:

| Category | Early Bird | Regular | Late | Includes |
|----------|------------|---------|------|----------|
| Student | $150 | $200 | $250 | Full conference access |
| Academic | $350 | $450 | $550 | Full conference access |
| Industry | $600 | $750 | $900 | Full conference access |
| Virtual | $50 | $75 | $100 | Streaming access only |

**Registration Periods**:
- Early Bird: March 1 - April 30
- Regular: May 1 - July 15
- Late: July 16 - August 1
- On-site: August 8-10 (limited)

### What's Included

**Standard Registration**:
- All keynote sessions
- Choice of tutorials/workshops
- Conference materials
- Welcome reception
- Coffee breaks and lunch
- Conference dinner (optional add-on)
- Access to recorded sessions post-event

## Registration Form Setup in Indico

### Creating Your Registration Form

**Navigation**: Event Management → Registration → Create Form

**Essential Fields to Configure**:
- Personal Information (name, email, affiliation)
- Registration category (Student/Academic/Industry/Virtual)
- Dietary requirements and accessibility needs
- Workshop and tutorial preferences
- Additional options (conference dinner, etc.)

### Using Indico's Form Builder

**Field Types Available**:
- **Text fields**: Names, affiliations
- **Dropdowns**: Countries, registration types
- **Checkboxes**: Dietary restrictions, interests
- **File uploads**: Student ID verification
- **Number fields**: Group registrations
- **Date pickers**: Arrival/departure for hotels

### Smart Form Features

**Conditional Sections**:
- Show/hide fields based on selections
- Different prices for different categories
- Capacity limits for workshops
- Automatic waitlists when full

## Abstract Submission System

### Call for Abstracts Module

The Call for Abstracts in Indico handles the entire submission workflow. Based on the useR! 2025 setup:

**Key Dates**:
- Call opens: March 11, 2025
- Submission deadline: 7:59 AM (USEastern)
- Configured directly in Indico with automatic enforcement

### Submission Configuration

**Standard Workflow**:
1. Authors access Call for Abstracts page
2. Click "Submit new abstract" 
3. Fill in required fields
4. Submit for review
5. Track status in their Indico account

**Form Fields (useR! 2025)**:
- Title and abstract text
- Authors and affiliations 
- Contribution type selection
- Topic/track assignment
- Any custom fields needed

### Review Management

**Built-in Features**:
- **Reviewing Teams**: Configure reviewers and their permissions
- **Review Questions**: Set scoring criteria and review forms
- **Automated Notifications**: System handles all communications
- **Conflict Management**: Track and manage conflicts of interest
- **Decision Workflow**: Accept/reject with automatic notifications

## Payment Methods

### Credit Card Processing

**Supported Cards**:
- Visa, Mastercard, American Express
- Regional cards (based on location)
- 3D Secure authentication
- Saved cards for returning attendees

### Alternative Payment Methods

**Wire Transfers**:
```
Bank: Wells Fargo
Account Name: Duke University
Account Number: [provided separately]
Reference: useR2025-[RegistrationID]

Note: Add $25 processing fee for wire transfers
```

**Purchase Orders or Invoices**:
- For institutional payments
- Net 30 terms available
- Requires approval process
- Invoice generated automatically

**Checks** (if accepted):
- Payable to: Host Institution
- Mail to: [Conference Address]
- Processing time: 2-3 weeks

## Financial Support Programs

### Student Travel Grants

**Application Process**:
1. Register with student rate
2. Complete grant application in Indico
3. Submit supporting documents:
   - Letter from advisor
   - CV/Resume
   - Statement of need
   - Abstract (if presenting)

**Selection Criteria**:
- Financial need
- Geographic diversity
- Underrepresented groups
- Abstract quality (if applicable)

### Fee Waivers

**Eligibility**:
- Participants from developing countries
- Unemployed/between positions
- Special circumstances

**Process**:
- Email request to organizers
- Provide justification
- Decision within 5 business days
- Code provided for registration

### Diversity Scholarships

**Target Groups**:
- Underrepresented minorities in tech
- First-generation college students
- Career changers
- Non-traditional paths

## Registration Management

### Monitoring in Indico

**Built-in Reports**:
- Registration statistics dashboard
- Financial summary reports  
- Participant lists with filters
- Abstract submission tracking
- Custom field analytics

**Indico Dashboard Features**:
- Real-time registration numbers
- Revenue tracking
- Attendee demographics
- Abstract submission statistics
- Session capacity monitoring

### Capacity Management

**Handling Sold-Out Situations**:
1. Implement waitlist automatically
2. Increase virtual attendance options
3. Consider venue overflow options
4. Prioritize based on registration date
5. Communicate clearly about status

### Email Management in Indico

**Automatic Emails**:
Indico sends these automatically:
- Registration confirmation with receipt
- Payment confirmations
- Abstract submission confirmations
- Review decisions
- Reminder emails (configurable)

**Customizing Email Templates**:
1. Go to Event Management → Customize
2. Select Email Templates
3. Edit templates with your branding
4. Use placeholders for dynamic content:
   - {name}, {event_title}, {registration_id}
   - {amount}, {dates}, {abstract_title}

**Mass Communication**:
- Send to all participants or filtered groups
- Schedule emails in advance
- Track open rates and bounces

## Badge Generation with Indico

### Using Indico's Badge Designer

**Access**: Event Management → Registration → Badges

**Design Features**:
- Drag-and-drop badge designer
- Include participant data fields
- Add logos and graphics
- QR codes for check-in
- Color coding by registration type
- Multiple badge templates

### Badge Production

**Export and Print**:
1. Design badge template in Indico
2. Generate PDF with all badges
3. Send to professional printer or print in-house
4. Sort alphabetically for easy distribution

## Common Issues and Solutions

### Registration Troubleshooting

**Payment Issues**:
- Check Stripe dashboard for detailed error
- Offer manual payment option
- Send payment link via email
- Accept bank transfers as backup

**Access Problems**:
- Use Indico's password reset feature
- Check spam folders for emails
- Verify email address spelling
- Admin can manually create accounts

**Form Issues**:
- Test form with different browsers
- Check required field settings
- Verify price calculations
- Review capacity limits

## Privacy and Data Management

### GDPR Compliance in Indico

**Built-in Privacy Features**:
- Consent checkboxes on registration
- Data retention settings
- Right to deletion tools
- Export participant data
- Privacy notices on forms

### Setting Up Consent Options

**In Registration Form**:
1. Add "Legal" section to form
2. Include required consent checkboxes:
   - Terms and conditions (required)
   - Photo/video consent (optional)
   - Marketing communications (optional)
3. Link to privacy policy
4. Configure data retention period

### Data Security

**What Indico Provides**:
- Encrypted connections (HTTPS)
- Secure payment handling
- Role-based access control
- Audit logs
- Regular security updates

## Check-in Process

### On-Site Registration

**Setup Requirements**:
- Multiple check-in stations
- Alphabetical division
- Express lane for pre-printed badges
- Problem resolution desk
- On-site registration capability

### Check-in with Indico

**Indico Check-in App**:
- QR code scanning from badges
- Real-time synchronization
- Works offline with sync
- Multiple check-in points

**Backup Process**:
- Export attendee list from Indico
- Print alphabetical lists
- Manual check-off if needed
- On-site registration desk

## Post-Conference Tasks

### Data Export from Indico

**Export Options**:
- Participant list (CSV/Excel)
- Financial reports
- Abstract book (PDF)
- Registration statistics
- Custom reports

### Archive the Conference

**In Indico**:
1. Export all data before archiving
2. Generate final reports
3. Download invoices and receipts
4. Back up the entire event
5. Keep read-only access for reference

### Financial Wrap-up

**Using Indico Reports**:
- Export payment summary
- Generate tax documents
- Process final refunds
- Reconcile with Stripe dashboard
- Create final budget report

## Simplified Setup Timeline

### 6 Months Before
- [ ] Get Indico access (university or hosted)
- [ ] Create conference event
- [ ] Set up Stripe account
- [ ] Build registration form
- [ ] Configure pricing and test payments

### 4 Months Before  
- [ ] Open early registration
- [ ] Enable abstract submission
- [ ] Set up automatic emails
- [ ] Create financial tracking

### 2 Months Before
- [ ] Monitor registration numbers
- [ ] Design and test badges
- [ ] Plan check-in logistics
- [ ] Prepare participant communications

### Conference Week
- [ ] Export final lists from Indico
- [ ] Print badges
- [ ] Set up check-in stations
- [ ] Brief registration team
- [ ] Have backup plans ready

## Next Steps

With registration systems in place, proceed to:
- [Sponsorship](05-sponsorship.md) - Managing sponsor registrations
- [Program Planning](06-program-planning.md) - Coordinating speaker registration
- [Committees & Volunteers](08-committees-volunteers.md) - Managing staff registration
---

**Navigation**: [← Website Development](03-website-development.md) | [Sponsorship →](05-sponsorship.md)
