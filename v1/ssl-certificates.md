---
layout: doc
title: SSL Certificates
---

# SSL Certificates

SSL certificates are a must for any site that has authentication or payment processing. In this guide, we will walk through the steps to request, purchase, and install an SSL certificate to your WarpSpeed server.

**Note: SSL Certificates must be purchased from a third party. Sites like [NameCheap](https://www.namecheap.com/) offer certificates for around $9 per year.**

## Creating a Certificate Signing Request (CSR)

The first step in getting an SSL certificate installed is to make a request for one. The request is called a Certificate Signing Request (CSR). A certificate issuer/signing authority can then take your CSR and provide you with a signed certificate that you can install on your server. By doing this, you establish a chain of trust back to a "trusted" signing authority, and then your browser will show the little green lock in the title bar and traffic to and from your site can be encrypted.

To create a CSR for your site, perform the following:

1. Login to your WarpSpeed account [here](https://warpspeed.io/login).
1. Access your "My Servers" dashboard and click on the "Manage" button next to the server your site is on.
1. Access your site details by clicking on the "Manage" button for the site you want to add the certificate to.
1. Click on the "SSL Certificates" tab.
1. Fill in the CSR form (make use of the provided hints). Note: Do not use anything but alphanumeric characters in the form. Sometimes something like a comma in a company name can cause strange issues when the CSR is being processed by third parties.
1. Click Generate CSR when you have filled out all the form fields.
1. Scroll down to the bottom of the page to see your request. Click on the "View CSR" button in the CSR column.
1. Copy the entire code block to your clipboard. You will need this to purchase your certificate.

## Purchase a Certificate

You may purchase a certificate from wherever you'd like. We often choose a RapidSSL or Comodo cert from [NameCheap](https://www.namecheap.com/) as they are very affordable and also have good overall compatibility.

You pay for certificates by the year. The certificate will need to be approved by an owner of the domain before it will be issued. This is generally done by sending an email to `admin@domain.com` with a link to click for approving the certificate request.

Once the request is approved, you will be provided with an SSL certificate that can then be installed on your server. Very often, the certificate will come with additional certificates that must be added to create the full trust chain. More details on this below.

## Installing a Certificate

Once you have purchased and obtained a certificate, you can install it. To do so, perform the following:

1. Access the site management page for your site.
1. Click on the "SSL Certificates" tab.
1. Locate the certificate request you made in the "Exiting Site Certificates" table at the bottom and then click the "Install" button on the correct row.
1. Paste the entire certificate you received into the dialog. If additional certificates were provided to complete the chain, paste those below your primary certificate.
1. Click save to add the certificate. This will add the certificate to the server, but it will not be active.

## Activating a Certificate

Once you have installed a certificate, you can activate it.

1. Access the site management page for your site.
1. Click on the "SSL Certificates" tab.
1. Locate the installed certificate in the "Exiting Site Certificates" table at the bottom and then click the "Activate" button on the correct row.
1. Now, you need to reload the site configuration to make the change take effect. To do so, scroll up and click the "Configuration" tab and then click the "Site Reload" button.

**Note: If an error occurs during restarting, you will need to resolve it by manually editing the site configuration files and then performing another "Site Reload".**
