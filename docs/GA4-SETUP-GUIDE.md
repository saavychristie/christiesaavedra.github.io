# Google Analytics 4 Setup Guide
## For Christie Saavedra's Portfolio

---

## Step 1: Create a Google Analytics 4 Property

1. Go to [analytics.google.com](https://analytics.google.com)
2. Sign in with your Google account
3. Click **Admin** (gear icon, bottom left)
4. Click **+ Create Property**
5. Fill in:
   - **Property name:** `Christie Saavedra Portfolio`
   - **Timezone:** Your timezone
   - **Currency:** USD
6. Click **Next** → Select **Business size** → Click **Create**
7. Choose **Web** as your platform
8. Enter:
   - **Website URL:** `https://christiesaavedra.com`
   - **Stream name:** `Portfolio Main`
9. Click **Create stream**

---

## Step 2: Get Your Tracking Code

After creating the stream, you'll see your **Measurement ID** (looks like `G-TKJH0YKZT5`).

Copy this code snippet (replace `G-TKJH0YKZT5` with your actual ID):

```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-TKJH0YKZT5"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-TKJH0YKZT5');
</script>
<!-- End Google Analytics 4 -->
```

---

## Step 3: Add to Your Portfolio Pages

Add the tracking code to the `<head>` section of each HTML file:

### Files to Update:
| File | Description |
|------|-------------|
| `index.html` | Main portfolio page |
| `dashboard.html` | Healthcare Dashboard case study |
| `xacteched-campaign.html` | XactechED Campaign case study |
| `arizona-esthetics.html` | Arizona Esthetics case study |
| `palmview-lab.html` | Palmview Lab case study |

### Where to Add It:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- ADD GOOGLE ANALYTICS HERE (right after meta tags) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-TKJH0YKZT5"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-TKJH0YKZT5');
    </script>
    <!-- END GOOGLE ANALYTICS -->
    
    <title>Christie Saavedra | Portfolio</title>
    <!-- rest of your head content -->
</head>
```

---

## Step 4: Configure UTM Tracking (Automatic!)

Good news: **GA4 automatically tracks UTM parameters!** 

When someone visits your site using a link like:
```
https://christiesaavedra.com?utm_source=linkedin&utm_medium=job-application&utm_campaign=acme-corp-dec2024
```

GA4 will automatically capture:
- **Source:** linkedin
- **Medium:** job-application  
- **Campaign:** acme-corp-dec2024

---

## Step 5: Create Your Tracking Dashboard

### View Traffic Sources:
1. In GA4, go to **Reports** → **Acquisition** → **Traffic acquisition**
2. You'll see all traffic broken down by source/medium

### View Campaign Performance:
1. Go to **Reports** → **Acquisition** → **Traffic acquisition**
2. Click the dropdown that says "Session default channel group"
3. Change to **Session campaign**
4. Now you'll see each company/application as a separate row!

### Create a Custom Report (Recommended):

1. Go to **Explore** (left sidebar)
2. Click **+ Blank**
3. Name it: "Application Tracking"
4. Add these **Dimensions** (drag to Rows):
   - Session campaign
   - Session source
   - Page path
5. Add these **Metrics** (drag to Values):
   - Sessions
   - Engaged sessions
   - Average engagement time per session
   - Engagement rate
6. Click **Save**

---

## What You'll Be Able to See

### Per Company/Application:
| Metric | What It Tells You |
|--------|-------------------|
| **Sessions** | How many times they visited |
| **Users** | How many unique people visited |
| **Engaged Sessions** | Visits longer than 10 seconds |
| **Avg. Engagement Time** | How long they spent reading |
| **Pages per Session** | How many pages they viewed |
| **Engagement Rate** | % of visits that were meaningful |

### Example Insights:
- "Acme Corp has visited 4 times and spent an average of 3 minutes"
- "They viewed the Healthcare Dashboard 3 times"
- "TechStart looked at 5 different pages - they're thorough!"
- "HealthCo bounced after 10 seconds - probably not a fit"

---

## Pro Tips

### 1. Set Up Email Reports
1. Go to **Admin** → **Scheduled emails**
2. Create a weekly report showing campaign performance
3. Get notified when companies are viewing your portfolio

### 2. Track Specific Button Clicks (Optional)
If you want to know when someone downloads your resume or clicks "Contact":

```javascript
// Add to your page's JavaScript
document.querySelector('.resume-download').addEventListener('click', function() {
  gtag('event', 'resume_download', {
    'event_category': 'engagement',
    'event_label': 'Resume PDF'
  });
});

document.querySelector('.contact-button').addEventListener('click', function() {
  gtag('event', 'contact_click', {
    'event_category': 'engagement',
    'event_label': 'Contact Button'
  });
});
```

### 3. Set Up Alerts
1. Go to **Admin** → **Custom definitions** → **Custom insights**
2. Create an alert for "Sessions > 0 from new campaigns"
3. Get notified when a new company views your portfolio

---

## Testing Your Setup

1. **Install the Tag Assistant Chrome extension** from Google
2. Visit your portfolio with a UTM link
3. Check that the GA tag is firing correctly
4. Wait 24-48 hours for data to appear in reports (real-time data is available immediately under **Reports** → **Realtime**)

### Test Link:
```
https://christiesaavedra.com?utm_source=test&utm_medium=verification&utm_campaign=ga4-setup-test
```

Visit this link, then check **Realtime** in GA4 - you should see yourself!

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| No data showing | Wait 24-48 hours; check Realtime first |
| Tag not firing | Verify code is in `<head>`, check for typos in Measurement ID |
| UTM not tracked | Make sure URL has `?` before first parameter |
| Blocked by ad blocker | Test in incognito or disable ad blocker |

---

## Quick Reference

**Your Measurement ID:** `G-TKJH0YKZT5` (replace with actual)

**UTM Parameter Format:**
```
?utm_source=SOURCE&utm_medium=job-application&utm_campaign=COMPANY-POSITION-MONTH
```

**GA4 Dashboard:** [analytics.google.com](https://analytics.google.com)

**Link Generator:** Use the included `utm-link-generator.html` tool

---

## Next Steps

1. ☐ Create GA4 property
2. ☐ Get Measurement ID
3. ☐ Add tracking code to all 5 HTML pages
4. ☐ Test with the verification link
5. ☐ Create your first tracked application link
6. ☐ Set up weekly email report
