# How to use email templates from HTMLemail.io

For bugs and problems please [create a new issue here](https://github.com/leemunroe/htmlemail/issues).

## Quickstart guide

How to try out these email templates as quickly as possible.

1. Go to [HTMLemail.io](http://htmlemail.io) and download the templates.
2. Unzip `htmlemail.zip`. You should now have files that look like [this](https://cloud.githubusercontent.com/assets/15963/17390151/353c0312-59bf-11e6-86ba-4761a85cf555.png).
3. Open up [PutsMail](https://putsmail.com/tests/new) and create a new test email. Enter your email as the recipient.
4. Open up one of the inlined emails `alert-success-inlined.html` in your favorite editor. Copy and paste the code into PutsMail like [this](https://cloud.githubusercontent.com/assets/15963/17390249/1a40e266-59c0-11e6-8018-6b7dbbb9a206.png).
5. Check your inbox to see a [preview of your email](https://cloud.githubusercontent.com/assets/15963/17390295/a9af54f0-59c0-11e6-9959-2ca4ba294621.png).

🎉

## Working with inline CSS

These emails come packaged with both inlined CSS and a CSS stylesheet.

![image](https://cloud.githubusercontent.com/assets/15963/17390151/353c0312-59bf-11e6-86ba-4761a85cf555.png)

CSS stylesheets are great for ensuring all your emails are consistent as you can manage styles in one place.

However, before you send your HTML email, you need to inline the CSS as some email clients do not render CSS that **is not** inlined.

### How to inline CSS

Option one is to use the templates that are already inlined, and continue to write any new styles inline. But as mentioned these are harder to work with as it is harder to maintain your styles.

Option two is to use an inline CSS tool. Copy and paste your email into an inliner and it will inline the CSS for you. I like using [Premailer](http://premailer.dialect.ca/). Putsmail, Zurb, Campaign Monitor and Mailchimp all have good inliner tools.

Option three, you can rely on your ESP (email service provider) to do the work for you. For example, you can set Mailchimp to automatically inline CSS for you before sending your campaign.

## Working with images in email

These emails come packages with retina ready image assets and some stock photography.

![image](https://cloud.githubusercontent.com/assets/15963/17390518/9c819732-59c2-11e6-9371-2b111ad26e8d.png)

In order for these to work they need to be uploaded somewhere and available via the web. The `src` then has to reference the full path of the image.

The good news is if you're using an ESP like Mailchimp, Campaign Monitor, Salesforce or any other marketing service, they will let you upload the images. If you're using an API service like Mailgun or Sendgrid you may have to upload the images yourself to your own CDN.

For example, I've uploaded my logo to a CDN. In the header here I would replace `img/logo.png` with my logo's full CDN path.

```html
<img src="img/logo.png">
```

```html
<img src="http://1bb070fe7102b70b7b9b-8d9a58972604befd3cf8b483887bb2bb.r27.cf2.rackcdn.com/img/logo.png">
``` 

## Working with Mailchimp (and other ESPs)

Mailchimp has great tools to make it easy for you to import HTML templates.

1. Zip up your email template. You should include one html file, your `main.css` file and your `img` folder.
1. Open up `Templates`, click `New Template` and select `Import zip`. Select your zip file and give it a name. [Screenshot](https://cloud.githubusercontent.com/assets/15963/17390732/a2d00ee6-59c4-11e6-9cdd-5a93218bec74.png).
2. If your zip file was set up right, that should be it. Now use Mailchimp's [templating language](http://templates.mailchimp.com/getting-started/template-language/) and [merge tags](http://templates.mailchimp.com/getting-started/merge-tags/) to customize your template.

![image](https://cloud.githubusercontent.com/assets/15963/17390732/a2d00ee6-59c4-11e6-9cdd-5a93218bec74.png)

## More support

[Create a issue](https://github.com/leemunroe/htmlemail/issues) or email hello@htmlemail.io
