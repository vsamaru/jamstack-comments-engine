*, ::after, ::before {
    -webkit-box-sizing: inherit;
    box-sizing: inherit;
}

user agent stylesheet
script {
    display: none;
}
.app-footer, .app-header, body {
    background: #0e1e24;
    color: #7b8488;
}
body {
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
    font-size: 16px;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
}
html {
    font-family: sans-serif;
    line-height: 1.15;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
}
*, ::after, ::before {
    -webkit-box-sizing: inherit;
    box-sizing: inherit;
}
*, ::after, ::before {
    -webkit-box-sizing: inherit;
    box-sizing: inherit;
}
::selection {
    background: #00ad9e;
    color: #fff;
}

![JAMstack Comments Engine screengrab](screenshot.jpg)


# Comments engine example.

Comments for your site. With no server to maintain and no Javascript dependency.


Built on Netlify

[![Netlify Status](https://api.netlify.com/api/v1/badges/9859aca9-0a82-49d4-9ae9-eefcbb4c4129/deploy-status)](https://app.netlify.com/sites/jamstack-comments/deploys)

## Setting up

1. Clone the repo and deploy it as a netlify (with one click via this DTN button)

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/philhawksworth/jamstack-comments-engine)

2. Configure a Slack integration on your Slack account
3. Add the required environment variables for:
  - `API_AUTH`
  - `APPROVED_COMMENTS_FORM_ID`
  - `SLACK_WEBHOOK_URL` (You'll need to create and configure [a Slack App](https://api.slack.com/apps?new_app=1))
4. **Add build hook** (`https://app.netlify.com/sites/{SITE_NAME}/settings/deploys#build-hooks`) which will rebuild and deploy the site whenever a new comment is submitted to the approved form
5. **Add a notification** (`https://app.netlify.com/sites/{SITE_NAME}/settings/forms#form-notifications`) which will call our build hook (above) when a new comment is added to the approved comments form.
6. **Add a notification** (`https://app.netlify.com/sites/{SITE_NAME}/settings/forms#form-notifications`) to call our comment handler lambda when a new comment is posted to the comments queue for approval.
