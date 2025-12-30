# Serverless Form Setup Guide

This guide explains how to configure the serverless contact/registration form for the Somali Fish Stock Training website.

## Overview

The website includes a contact and registration form (`contact.qmd`) that uses a serverless form submission service. This allows users to submit their information without requiring a backend server.

## Form Provider: Web3Forms

We use [Web3Forms](https://web3forms.com) - a free serverless form API that works perfectly with static sites hosted on GitHub Pages.

### Why Web3Forms?

- ✅ **Free forever** for up to 250 submissions/month
- ✅ **No backend required** - works with static sites
- ✅ **GDPR compliant**
- ✅ **Spam protection** included
- ✅ **Email notifications** to your inbox
- ✅ **No registration** for basic use
- ✅ **Works with GitHub Pages**

## Setup Instructions

### Step 1: Get Your Access Key

1. Visit [https://web3forms.com](https://web3forms.com)
2. Click "Get Started for Free"
3. Enter your email address (e.g., contact@tafiri.go.tz)
4. You'll receive an access key via email

### Step 2: Configure the Form

1. Open `/contact.qmd` in your repository
2. Find the CONFIG object at the top of the script section
3. Update the `ACCESS_KEY` value with your actual access key from Web3Forms

Example:
```javascript
const CONFIG = {
  ACCESS_KEY: "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  TIMEOUT_MS: 30000,
  CONTACT_EMAIL: "contact@tafiri.go.tz"
};
```

**Important Notes**:
- ✅ **Safe to commit**: Web3Forms access keys are designed for client-side use and are safe to commit to version control
- ✅ **Domain restricted**: Keys only work on domains registered with Web3Forms
- ✅ **Not a secret**: Unlike API secrets, these keys are meant to be visible in browser code
- ⚠️ **Update contact email**: Change `CONTACT_EMAIL` if you use a different support address
- ⚠️ **Update regional contacts**: The regional coordinator emails in the table are placeholders

### Step 3: Test the Form

1. Commit and push your changes to GitHub
2. Wait for GitHub Pages to deploy (usually 1-2 minutes)
3. Visit your website's contact page
4. Fill out the form with test data
5. Submit the form
6. Check the email address you registered with Web3Forms for the submission

## Alternative: Formspree

If you prefer to use Formspree instead:

1. Sign up at [https://formspree.io](https://formspree.io)
2. Create a new form and get your form endpoint
3. Update the fetch URL in `contact.qmd`:

```javascript
fetch('https://formspree.io/f/YOUR_FORM_ID', {
  method: 'POST',
  headers: {
    'Accept': 'application/json'
  },
  body: JSON.stringify(data)
})
```

## Alternative: Google Forms

For a simpler approach using Google Forms:

1. Create a Google Form with the desired fields
2. Get the embed code or link
3. Replace the HTML form in `contact.qmd` with an iframe:

```html
<iframe src="YOUR_GOOGLE_FORM_URL" width="640" height="1200" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
```

## Form Fields

The current form collects:

- Full Name (required)
- Email Address (required)
- Phone Number (optional)
- Region (required) - dropdown with 6 regions + Other
- Organization/Institution (required)
- Position/Role (optional)
- Fisheries Experience (required) - dropdown
- Module of Interest (optional) - dropdown
- Additional Information (optional) - text area
- Consent checkbox (required)

## Customization

### Adding Fields

To add a new field to the form:

1. Add the HTML input in `contact.qmd`:
```html
<div class="mb-3">
  <label for="new-field" class="form-label">New Field Label *</label>
  <input type="text" class="form-control" id="new-field" name="new-field" required>
  <div class="invalid-feedback">
    Please provide this information.
  </div>
</div>
```

2. The field will automatically be included in the submission

### Changing Email Subject

Update the hidden field in `contact.qmd`:
```html
<input type="hidden" name="_subject" value="Your Custom Subject">
```

### Adding Auto-Reply

With Web3Forms, add a hidden field:
```html
<input type="hidden" name="_autoresponse" value="Thank you for registering! We'll contact you soon.">
```

## Spam Protection

Web3Forms includes built-in spam protection. For additional protection:

1. **Honeypot field** (already included):
```html
<input type="hidden" name="_honeypot" value="">
```

2. **Google reCAPTCHA** - Add to Web3Forms dashboard settings

## Email Notifications

Submissions are sent to the email address registered with Web3Forms. To add multiple recipients:

1. In Web3Forms dashboard, add CC email addresses
2. Or use the form field:
```html
<input type="hidden" name="_cc" value="additional@email.com">
```

## Data Storage

- Web3Forms stores submissions for 30 days (free plan)
- Download submissions from your Web3Forms dashboard
- For longer storage, upgrade to a paid plan or export regularly

## Troubleshooting

### Form not submitting

1. Check that you've added your access key
2. Check browser console for JavaScript errors
3. Verify the form action URL is correct
4. Ensure all required fields are filled

### Not receiving emails

1. Check spam/junk folder
2. Verify email address in Web3Forms account
3. Check Web3Forms dashboard for submission logs

### Styling issues

The form uses Bootstrap 5 classes (included in Quarto). If styling looks wrong:
1. Ensure Quarto is rendering properly: `quarto render`
2. Check that Bootstrap CSS is loaded in the output HTML

## Security Best Practices

1. ✅ **Never commit API keys** to version control (form keys are safe for client-side use)
2. ✅ **Use HTTPS** (GitHub Pages provides this automatically)
3. ✅ **Validate inputs** (already implemented with HTML5 validation)
4. ✅ **Enable spam protection** in Web3Forms dashboard
5. ✅ **Monitor submissions** regularly for abuse

## Support

- **Web3Forms Documentation:** https://docs.web3forms.com
- **Quarto Documentation:** https://quarto.org
- **Form Issues:** Check `/contact.qmd` for inline comments
- **General Questions:** contact@tafiri.go.tz

## License

This form implementation is part of the Somali Fish Stock Training Program and is licensed under CC BY 4.0.

---

**Last Updated:** December 2024
**Maintained By:** TAFIRI Training Program Team
