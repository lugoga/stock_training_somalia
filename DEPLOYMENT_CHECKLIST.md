# Deployment Checklist

Use this checklist to verify the serverless form is correctly deployed and functional.

## Pre-Deployment Checklist

### 1. Access Key Configuration
- [ ] Web3Forms account created
- [ ] Access key received via email
- [ ] Access key added to `contact.qmd` CONFIG.ACCESS_KEY
- [ ] CONFIG.CONTACT_EMAIL verified (currently: contact@tafiri.go.tz)
- [ ] CONFIG.TIMEOUT_MS reviewed (currently: 30000ms / 30 seconds)

### 2. Contact Information
- [ ] Regional coordinator emails reviewed
- [ ] Regional coordinator emails updated if needed (currently placeholder @fisheries.so)
- [ ] Main contact email verified in multiple locations:
  - [ ] contact.qmd (CONFIG and form text)
  - [ ] about.qmd
  - [ ] README.md
  - [ ] _quarto.yml footer

### 3. Documentation Review
- [ ] SERVERLESS_FORM_SETUP.md reviewed for accuracy
- [ ] CONTACT_FORM_FEATURES.md reviewed
- [ ] EMAIL_TEMPLATES.md ready for coordinators
- [ ] IMPLEMENTATION_SUMMARY.md accurate
- [ ] README.md updated with contact form links

### 4. Code Quality
- [ ] All code review comments addressed
- [ ] Error handling implemented (timeout, network, server errors)
- [ ] Privacy consent text updated
- [ ] Access key validation working
- [ ] Configuration variables centralized in CONFIG object

### 5. Git Repository
- [ ] All changes committed
- [ ] Commit messages clear and descriptive
- [ ] Changes pushed to remote repository
- [ ] Branch: copilot/add-serverless-form-quarto
- [ ] Ready for merge to main branch

## Deployment Process

### Step 1: Merge to Main
```bash
# Review the changes one final time
git log --oneline -5

# Checkout main branch
git checkout main

# Merge the feature branch
git merge copilot/add-serverless-form-quarto

# Push to GitHub
git push origin main
```

### Step 2: Verify GitHub Pages Deployment
- [ ] GitHub Actions workflow triggered
- [ ] Workflow completed successfully
- [ ] No deployment errors in Actions log
- [ ] Typical deployment time: 1-3 minutes

### Step 3: Access Website
- [ ] Visit the deployed website URL
- [ ] Navigate to Contact page via navigation menu
- [ ] Page loads without errors
- [ ] Form displays correctly
- [ ] No JavaScript console errors

## Post-Deployment Testing

### Visual Verification
- [ ] **Navigation**: "Contact" link visible in navbar
- [ ] **Page Layout**: Contact page displays properly
- [ ] **Form Styling**: Bootstrap styling applied correctly
- [ ] **Responsive Design**: Form looks good on mobile (resize browser)
- [ ] **Regional Table**: Regional contacts table displays
- [ ] **FAQ Section**: FAQ section displays

### Form Functionality Testing

#### Test 1: Access Key Not Configured
If you haven't added the access key yet:
- [ ] Try submitting the form
- [ ] Should see red error: "Configuration Required"
- [ ] Error includes email link and setup documentation link
- [ ] Form button re-enables after error

#### Test 2: Form Validation
- [ ] Try submitting empty form
- [ ] Required fields show validation errors
- [ ] Email field validates email format
- [ ] Consent checkbox is required
- [ ] Form highlights invalid fields in red

#### Test 3: Successful Submission (After Access Key Added)
- [ ] Fill out all required fields with valid data
- [ ] Click "Submit Registration"
- [ ] Button shows loading spinner
- [ ] Success message appears (green alert)
- [ ] Form resets after successful submission
- [ ] Check configured email inbox for submission

#### Test 4: Error Handling
To test error handling (before configuring access key):
- [ ] Fill out form
- [ ] Submit
- [ ] Verify helpful error message displays
- [ ] Error message includes fallback email contact
- [ ] Button re-enables for retry

### Mobile Responsiveness
Test on different screen sizes:
- [ ] Desktop (>1200px): Form looks good, readable
- [ ] Tablet (768-1199px): Form adapts correctly
- [ ] Mobile (320-767px): Form is usable, fields stack vertically
- [ ] Touch-friendly: Buttons and inputs are tappable
- [ ] Scrolling: Page scrolls smoothly

### Browser Compatibility
Test in multiple browsers:
- [ ] Chrome/Edge (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Mobile Safari (iOS)
- [ ] Chrome Mobile (Android)

### Email Notifications (After Access Key Configured)

#### Submit a Test Registration
Fill out form with:
- Name: Test User
- Email: your-test-email@example.com
- Region: Mogadishu
- Organization: Test Organization
- Experience: Intermediate
- Module Interest: All Modules
- Message: This is a test submission

Check that:
- [ ] Email received at configured address
- [ ] Email contains all form fields
- [ ] Email is formatted clearly
- [ ] Sender is Web3Forms (noreply@web3forms.com)
- [ ] Subject line is "New Training Registration"

## Performance Checks

### Page Load Performance
- [ ] Contact page loads in < 3 seconds
- [ ] No large image files slowing page
- [ ] JavaScript loads without delay
- [ ] Form renders immediately

### Form Submission Performance
- [ ] Submit completes in < 5 seconds (normal conditions)
- [ ] Loading spinner provides feedback
- [ ] Timeout protection works (triggers after 30 seconds)
- [ ] Error messages display promptly

## Security Verification

### HTTPS
- [ ] Site loads via HTTPS (padlock in browser)
- [ ] No mixed content warnings
- [ ] Certificate is valid

### Client-Side Validation
- [ ] HTML5 validation working
- [ ] JavaScript validation working
- [ ] Invalid data cannot be submitted

### Access Control
- [ ] Access key only works on registered domain
- [ ] Form cannot be hijacked for spam from other domains

## Analytics & Monitoring

### Optional: Setup Tracking
- [ ] Google Analytics configured (optional)
- [ ] Form submission events tracked (optional)
- [ ] Error events logged (optional)

### Web3Forms Dashboard
- [ ] Log in to Web3Forms dashboard
- [ ] Verify test submission appears
- [ ] Check submission count
- [ ] Review spam filter settings

## Documentation Verification

### For Users
- [ ] Contact page includes clear instructions
- [ ] Regional contacts are listed
- [ ] FAQ section answers common questions
- [ ] Fallback email contact always visible

### For Administrators
- [ ] SERVERLESS_FORM_SETUP.md is clear and complete
- [ ] EMAIL_TEMPLATES.md ready for coordinators
- [ ] CONTACT_FORM_FEATURES.md documents features
- [ ] IMPLEMENTATION_SUMMARY.md provides overview

### For Developers
- [ ] Code is well-commented
- [ ] Configuration is centralized
- [ ] Error handling is comprehensive
- [ ] Future enhancements documented

## Common Issues & Solutions

### Issue: Form not submitting
**Check:**
- Browser console for JavaScript errors
- Access key is configured correctly
- Internet connection is working
- Web3Forms service is online (status.web3forms.com)

### Issue: Email not received
**Check:**
- Spam/junk folder
- Email address in Web3Forms account is correct
- Web3Forms dashboard shows submission
- Email quota not exceeded (250/month on free tier)

### Issue: Styling looks wrong
**Check:**
- Quarto rendered the site correctly
- Bootstrap CSS is loading
- Custom CSS (styles.css) is loading
- Browser cache (try hard refresh: Ctrl+Shift+R)

### Issue: Regional emails not working
**Check:**
- Regional coordinator emails updated from placeholders
- Actual email addresses added
- Test sending email to each address

## Rollback Plan

If issues arise after deployment:

### Option 1: Quick Fix
```bash
# Fix the issue in contact.qmd or other files
git add .
git commit -m "Fix: [describe fix]"
git push origin main
# Wait for redeployment (1-3 minutes)
```

### Option 2: Revert Deployment
```bash
# Revert to previous version
git revert HEAD
git push origin main
# Wait for redeployment
```

### Option 3: Remove Contact Page Temporarily
```bash
# Remove Contact link from navigation
# Edit _quarto.yml and remove Contact menu item
git add _quarto.yml
git commit -m "Temporarily remove Contact link"
git push origin main
```

## Success Criteria

The deployment is successful when:
- ✅ Contact page is accessible via navigation
- ✅ Form displays correctly on all devices
- ✅ Form validation works properly
- ✅ Access key is configured (or helpful error shows)
- ✅ Submissions send emails successfully
- ✅ Error handling works for network issues
- ✅ Documentation is complete and accurate
- ✅ No console errors on contact page
- ✅ Mobile experience is good
- ✅ Regional contacts are accurate

## Final Sign-Off

**Deployment completed by**: _________________

**Date**: _________________

**Access Key Configured**: [ ] Yes [ ] No

**Test Submission Sent**: [ ] Yes [ ] No

**Test Email Received**: [ ] Yes [ ] No

**All Checks Passed**: [ ] Yes [ ] No

**Issues Noted**: _________________________________

**Ready for Production**: [ ] Yes [ ] No

---

## Next Steps After Deployment

1. **Monitor submissions** for the first week
2. **Respond promptly** to test and real registrations
3. **Gather feedback** from users about form experience
4. **Track metrics**: submission rate, completion time, errors
5. **Iterate based on feedback** and usage patterns
6. **Update regional contacts** as they become available
7. **Train coordinators** on using email templates
8. **Document any issues** and solutions for future reference

## Support

For deployment issues:
- **Technical**: Check browser console and GitHub Actions logs
- **Configuration**: See SERVERLESS_FORM_SETUP.md
- **Form issues**: See CONTACT_FORM_FEATURES.md
- **Questions**: contact@tafiri.go.tz

---

**Version**: 1.0  
**Last Updated**: December 2024  
**Maintained By**: TAFIRI Training Program Team
