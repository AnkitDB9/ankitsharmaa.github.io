# Email Service Configuration

To enable the contact form to send emails to your inbox, you have several options:

## Option 1: EmailJS (Recommended - Free & Easy)

1. **Sign up at [EmailJS](https://www.emailjs.com/)**
2. **Create a new service** (Gmail, Outlook, etc.)
3. **Create an email template** with these variables:
   - `{{from_name}}` - sender's name
   - `{{from_email}}` - sender's email
   - `{{subject}}` - message subject
   - `{{message}}` - message content

4. **Update script.js** - Replace the `simulateEmailSend` function with:

```javascript
// Replace the simulateEmailSend function with this:
async function sendEmail(formData) {
    return emailjs.send(
        'YOUR_SERVICE_ID',    // Replace with your EmailJS service ID
        'YOUR_TEMPLATE_ID',   // Replace with your EmailJS template ID
        {
            from_name: formData.name,
            from_email: formData.email,
            subject: formData.subject,
            message: formData.message,
            to_email: 'your-email@ankitsharma.org'  // Your email
        },
        'YOUR_PUBLIC_KEY'     // Replace with your EmailJS public key
    );
}
```

5. **Add EmailJS script** to your HTML head:
```html
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>
    emailjs.init('YOUR_PUBLIC_KEY'); // Replace with your public key
</script>
```

## Option 2: Netlify Forms (If deploying on Netlify)

1. **Add `netlify` attribute** to your form:
```html
<form class="contact-form" id="contactForm" name="contact" method="POST" data-netlify="true">
    <input type="hidden" name="form-name" value="contact">
    <!-- rest of your form fields -->
</form>
```

2. **Update JavaScript** to handle Netlify form submission:
```javascript
async function sendEmail(formData) {
    const response = await fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: new URLSearchParams({
            'form-name': 'contact',
            ...formData
        }).toString()
    });
    
    if (!response.ok) {
        throw new Error('Network response was not ok');
    }
    
    return response;
}
```

## Option 3: Formspree (Alternative Service)

1. **Sign up at [Formspree](https://formspree.io/)**
2. **Create a new form** and get your form endpoint
3. **Update your form action**:
```html
<form class="contact-form" id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

4. **Update JavaScript**:
```javascript
async function sendEmail(formData) {
    const response = await fetch('https://formspree.io/f/YOUR_FORM_ID', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(formData)
    });
    
    if (!response.ok) {
        throw new Error('Network response was not ok');
    }
    
    return response;
}
```

## Current Setup

The contact form is currently set up with a simulation function. To activate real email sending:

1. Choose one of the options above
2. Follow the setup instructions
3. Replace the `simulateEmailSend` function call in `script.js` with your chosen email service
4. Test the form to ensure emails are being delivered

## Security Notes

- Never expose API keys in client-side code (EmailJS public keys are safe)
- Consider adding rate limiting to prevent spam
- Add form validation both client-side and server-side
- Consider adding a CAPTCHA for additional spam protection
