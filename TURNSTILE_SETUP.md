# Cloudflare Turnstile Setup Guide

## Quick Setup Steps

### 1. Get Your Turnstile Site Key

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. Navigate to **Turnstile** section
3. Click **Add Site**
4. Configure your site:
   - **Site name**: StopScamAds
   - **Domain**: 3ja.com (or your domain)
   - **Widget Mode**: Managed (recommended)
5. Copy your **Site Key**

### 2. Update index.html

Replace `YOUR_TURNSTILE_SITE_KEY` in index.html with your actual site key:

```html
<div class="cf-turnstile" data-sitekey="YOUR_ACTUAL_SITE_KEY_HERE"></div>
```

**Location**: Line ~485 in the form section

### 3. Test the Integration

1. Open your website
2. Scroll to the "Submit Scam Ads" section
3. Fill out the form
4. Complete the Turnstile verification
5. Click "Submit Report"

## API Endpoint

The form submits to:
```
POST https://scam-ads-collector.826364339.workers.dev/api/submit
```

## Form Fields

- **firstName**: User's first name (required)
- **lastName**: User's last name (required)
- **email**: User's email address (required)
- **platformType**: One of: youtube, tiktok, facebook, instagram, x, other (required)
- **videoLink**: HTTPS URL from Google Drive, Dropbox, OneDrive, or iCloud Drive (required)
- **turnstileToken**: Verification token from Turnstile widget (required)

## Rate Limits

- 5 submissions per IP per hour (enforced by the API)

## Supported Languages

The form automatically detects and supports:
- English (en)
- Chinese (zh)

## Troubleshooting

### Turnstile widget not showing
- Check that the Turnstile script is loaded: `https://challenges.cloudflare.com/turnstile/v0/api.js`
- Verify your site key is correct
- Check browser console for errors

### Form submission fails
- Ensure all required fields are filled
- Complete the Turnstile verification
- Check that the video link is from a supported platform (Google Drive, Dropbox, OneDrive, iCloud Drive)
- Verify you haven't exceeded the rate limit (5 submissions per hour)

### Error messages
- **"Please complete the verification"**: Complete the Turnstile challenge
- **"Invalid input data"**: Check that all fields are properly filled
- **"Failed to submit. Please try again."**: Network error or API is down

## Features Implemented

✅ Cloudflare Turnstile integration
✅ Multi-language support (EN/中文)
✅ Responsive design (mobile & desktop)
✅ Form validation
✅ Success/error messaging
✅ Auto-reset after successful submission
✅ Rate limiting protection
✅ Secure API submission

## Next Steps

1. Replace `YOUR_TURNSTILE_SITE_KEY` with your actual site key
2. Test the form on your local/staging environment
3. Deploy to production
4. Monitor submissions through your Cloudflare dashboard
