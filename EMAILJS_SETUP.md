# EmailJS Setup Guide for Portfolio Contact Form

## Overview
Your contact form is now integrated with EmailJS, which will allow visitors to send emails directly to you when they submit the form. Follow these steps to complete the setup.

## Step 1: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" and create a free account
3. Verify your email address

## Step 2: Create Email Service

1. After logging in, go to the **Email Services** section
2. Click **"Add New Service"**
3. Choose your email provider:
   - **Gmail** (recommended for personal use)
   - **Outlook/Hotmail**
   - **Yahoo**
   - Or any other supported service
4. Follow the setup instructions for your chosen service
5. **Copy the Service ID** (you'll need this later)

## Step 3: Create Email Template

1. Go to the **Email Templates** section
2. Click **"Create New Template"**
3. Set up your template with the following content:

### Template Settings:
- **Template Name**: Portfolio Contact Form
- **Subject**: New message from {{from_name}} - Portfolio Contact
- **Content** (HTML format):

```html
<p>You have received a new message from your portfolio website!</p>

<h3>Contact Details:</h3>
<p><strong>Name:</strong> {{from_name}}</p>
<p><strong>Email:</strong> {{from_email}}</p>

<h3>Message:</h3>
<p>{{message}}</p>

<hr>
<p><em>This email was sent from your portfolio contact form.</em></p>
```

4. **Copy the Template ID** (you'll need this later)

## Step 4: Get Your Public Key

1. Go to **Account** → **General**
2. Find your **Public Key** and copy it

## Step 5: Update Your Code

Open `js/script.js` and replace the placeholder values:

```javascript
// Replace line 231:
emailjs.init("YOUR_PUBLIC_KEY"); // Replace with your actual public key

// Replace line 275:
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
// Replace with your actual Service ID and Template ID
```

### Example:
```javascript
emailjs.init("abcdef123456789"); // Your actual public key
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

## Step 6: Configure Email Destination

In your EmailJS template settings:
1. Set the **To Email** field to: `taher.sadabar19@gmail.com` (or your preferred email)
2. You can also set up auto-reply if needed

## Step 7: Test the Form

1. Open your portfolio website
2. Fill out the contact form with test data
3. Submit the form
4. Check your email for the message

## Step 8: Email Template Variables

The form sends these variables that you can use in your EmailJS template:
- `{{from_name}}` - Visitor's name
- `{{from_email}}` - Visitor's email
- `{{message}}` - Visitor's message
- `{{to_name}}` - Your name (currently set to "Taher Sadabar")

## Troubleshooting

### Common Issues:

1. **"EmailJS is not defined" error**
   - Make sure the EmailJS CDN is loaded in your HTML
   - Check browser console for any loading errors

2. **Form submission fails**
   - Verify your Service ID, Template ID, and Public Key are correct
   - Check browser console for detailed error messages
   - Ensure your email service is properly configured

3. **Emails not received**
   - Check your spam/junk folder
   - Verify the template's "To Email" field is set correctly
   - Make sure your email service authentication is working

### Testing in Browser Console:

You can test your EmailJS configuration directly in the browser console:

```javascript
emailjs.send('your_service_id', 'your_template_id', {
    from_name: 'Test User',
    from_email: 'test@example.com',
    message: 'This is a test message'
}).then(function(response) {
    console.log('SUCCESS!', response);
}, function(error) {
    console.log('FAILED...', error);
});
```

## Security Notes

- EmailJS has built-in spam protection
- Your Public Key is safe to expose in frontend code
- Free EmailJS plan allows 200 emails per month
- Consider upgrading if you expect more traffic

## Support

- EmailJS Documentation: [https://www.emailjs.com/docs/](https://www.emailjs.com/docs/)
- EmailJS Support: Available through their dashboard

---

Once you've completed these steps, visitors to your portfolio will be able to send emails directly to you through the contact form!