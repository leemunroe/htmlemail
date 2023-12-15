# How to use email templates from [htmlemail.io](https://htmlemail.io)

For bugs and problems please [create a new issue here](https://github.com/leemunroe/htmlemail/issues).

## Quickstart guide

How to try out these email templates as quickly as possible.

1. Go to [htmlemail.io](https://htmlemail.io) and download the templates.
2. Unzip `htmlemail.zip`. You should now have files that look like [this](https://cloud.githubusercontent.com/assets/15963/17390151/353c0312-59bf-11e6-86ba-4761a85cf555.png).
3. Open up [Postdrop](https://postdrop.io) and create a new test email. Enter your email as the recipient.
4. Open up one of the inlined or embedded emails e.g. `alert-success-inlined.html` in your favorite editor. Make any copy changes you want to make. Copy and paste the code into Postdrop. Hit send.
5. Check your inbox to see a [preview of your email](https://cloud.githubusercontent.com/assets/15963/17390295/a9af54f0-59c0-11e6-9959-2ca4ba294621.png).

🎉

## Working with inline CSS

These emails come packaged with inlined CSS templates, embedded CSS templates and an external CSS stylesheet.

<img src="https://user-images.githubusercontent.com/15963/29856247-7229a2e0-8d06-11e7-9609-4bbe6d5b5c17.png" width="300">

CSS stylesheets are great for ensuring all your emails are consistent as you can manage styles in one place.

However, before you send your HTML email, you need to inline the CSS as some email clients do not render CSS that **is not** inlined.

### How to inline CSS

Option one is to use the templates that are already inlined, and continue to write any new styles inline. But as mentioned these are harder to work with as it is harder to maintain your styles.

Option two is to use an inline CSS tool. Copy and paste your email into our [CSS inliner](https://htmlemail.io/inline) and it will inline the CSS for you.

Option three, you can rely on your ESP (email service provider) to do the work for you. For example, you can set Mailchimp to automatically inline CSS for you before sending your campaign.

### Working with Sass/SCSS

If you purchased the pack with the original SCSS source files, you can make use of the special features [Sass](https://sass-lang.com/) has to offer.

* Install Sass on your system `npm install -g sass` or `brew install sass/sass/sass`
* In the `htmlemail` directory run the command `sass --watch scss/main.scss:main.css`

This will watch the `scss` folder for changes and when you update a file will compile the SCSS to `main.css`.

You can also use a [task runner](https://github.com/leemunroe/grunt-email-workflow) to help you automate the Sass compiling and inlining.

## Working with images in email

These emails come packaged with retina ready image assets and some stock photography.

![image](https://cloud.githubusercontent.com/assets/15963/17390518/9c819732-59c2-11e6-9371-2b111ad26e8d.png)

In order for these to work they need to be uploaded somewhere and available via the web. The `src` then has to reference the full path of the image.

The good news is if you're using an ESP like Mailchimp, Campaign Monitor, Salesforce or any other marketing service, they will let you upload the images. If you're using an API service like Mailgun or Sendgrid you may have to upload the images yourself to your own CDN.

For example, I've uploaded my logo to a CDN. In the header here I would replace `img/logo.png` with my logo's full CDN path.

```html
<img src="img/logo.png" alt="Useful alt text" width="200" height="40" border="0">
```

```html
<img src="http://1bb070fe7102b70b7b9b-8d9a58972604befd3cf8b483887bb2bb.r27.cf2.rackcdn.com/img/logo.png" alt="Useful alt text" width="200" height="40" border="0">
``` 

## Working with Mailchimp (and other ESPs)

Mailchimp has great tools to make it easy for you to import HTML templates.

1. Zip up your email template. You should include one html file, your `main.css` file and your `img` folder.
1. Open up `Templates`, click `New Template` and select `Import zip`. Select your zip file and give it a name. [Screenshot](https://cloud.githubusercontent.com/assets/15963/17390732/a2d00ee6-59c4-11e6-9cdd-5a93218bec74.png).
2. If your zip file was set up right, that should be it. Now use Mailchimp's [templating language](http://templates.mailchimp.com/getting-started/template-language/) and [merge tags](https://templates.mailchimp.com/getting-started/merge-tags/) to customize your template.

![image](https://cloud.githubusercontent.com/assets/15963/17390732/a2d00ee6-59c4-11e6-9cdd-5a93218bec74.png)

[Check out our blog](https://htmlemail.io/blog/) for more setup tutorials.

## Changelog

### December 15 2023
* Accessibility: Added `lang=en` to HTML tags

### November 29 2023
* Accessibility: default font size changes to 16px
* Accessibility: added `role=presentation` to tables so screen readers know tables are for layout purposes
* Accessibility: changed default color values for improved contrast and dark mode support
* Design: updated to a more modern default color palette
* Design: added rounded corners and spacing to reflect modern design trends
* Assets: added social icons for X and Threads, and updated Twitter, Facebook, YouTube, Instagram, LinkedIn, Pinterest for dark mode support
* Assets: added app store images for Microsoft, and updated Apple, Google, Amazon
* Sass (Developer Edition): cleaned up variables so all colors, type, spacing, borders are using tokens

### June 25 2019
* Added source SCSS files to unlimited license pack
* Added styles for Samsumg mobile that stops numbers turning into links

### June 27 2018
* Adjust all spacing to a 8px base
* Remove capital "M" from `margin` as no longer needed as fix for Outlook

### August 29 2017
* Added new ecommerce promotional template
* Added new RSS to email news template
* Added embedded CSS versions to the pack for each template
* Added a more bullet proof horizontal rule solution that works in Outlook
* Modified license changing "multi license" to "unlimited license"
* Removed `width: auto !important` from `.container` style which was affecting Outlook when left as embedded CSS

### January 16 2017
* Added better support for ordered and unordered bullet lists
* Fixed a receipt table alignment issue in versions of Outlook by introducing a `receipt-container` element and class - wrap the receipt table with this container to ensure it is centered in Outlook
* Updated the Instagram and Google Play store icons

### August 19 2016
* Removed `display: block;` from the `container` div as it was causing issues in Gmail for iPhone [#2](https://github.com/leemunroe/htmlemail/issues/2)
* Added explicit styles for article heading links to stop default blue being used in Outlook
* Added an Outlook conditional statement to fix image rendering issues in Outlook 2013 120 DPI
* Updated the `license.txt` to help clarify some questions around licensing and reselling

## More support

[Create a issue](https://github.com/leemunroe/htmlemail/issues) or email hello@htmlemail.io
