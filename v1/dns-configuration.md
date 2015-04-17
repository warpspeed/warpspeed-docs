---
layout: doc
title: DNS Configuration
---

# DNS Configuration

DNS is an acronmy that stands for [Domain Name System](http://en.wikipedia.org/wiki/Domain_Name_System). DNS provides a way to map computer addresses like 123.123.123.123 to something we can remember like warpspeed.io. When you configure a new server with WarpSpeed and begin setting up your sites, you will need to purchase a domain name and set up the DNS entries to point to your new server's address.

## Topics

- [Purchasing a domain.](#purchase-a-domain)
- [Configuring DNS.](#configuring-dns-and-nameservers)
- [Testing before DNS propagation.](#testing)

## <a name="purchase-a-domain"></a>Purchasing a Domain.

Just go to your favorite domain registrar and search for a domain name you'd like to buy. Finding an available name that you like will be the hardest part. Complete the checkout and you are ready to go!

## <a name="configuring-dns-and-nameservers"></a>Configuring DNS and nameservers.

We recommend that you setup your DNS on your hosting provider, Digital Ocean or Linode. In order for this to work, you will have to configure nameservers within your domain registrar. Nameservers tell what servers should be used for DNS on a particular domain.

Follow these guides:

1. Setup DNS on Digital Ocean or Linode by following one of these guides.
	- [Digital Ocean DNS guide](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-host-name-with-digitalocean)
	- [Linode DNS guide](https://www.linode.com/docs/networking/dns/dns-manager)
1. Make sure you set up your domain to use the appropriate nameservers. If you are having trouble, try searching google for "custom nameservers" followed by the name of the company you purchased your domain with.

## <a name="testing"></a>Testing before DNS propagation.

Once DNS is configured, it sometimes takes up to 24 hours update and take effect. In the meanwhile, you can access your site by name if you configure an entry in your "hosts" file. The hosts file is a special file that your computer looks at before it goes to look up names in DNS.

Follow the instructions below to edit your hosts file:

- Mac Users
	1. Open a termial window.
	1. Type `sudo nano /etc/hosts`
	1. Add an entry that looks like this: `123.123.123.123  domain.com`. There should only be one entry per line. Make sure you replace the example address and domain with the actual values. The address value should be the address of your WarpSpeed server.
	1. Save and close the file. You will need to provide your account password.

- Windows Users
	1. Open the following file in Notepad with administration privledges: `c:\Windows\System32\Drivers\etc\hosts`.
	1. Add an entry that looks like this: `123.123.123.123  domainn.com`. There should only be one entry per line. Make sure you replace the example address and domain with the actual values. The address value should be the address of your WarpSpeed server.
	1. Save and close the file.

Using the process above, you can even add addresses you do not own or addresses that are just for testing such as `domain.dev`. Keep in mind that the addresses you enter will only work on your computer. Also, don't forget to remove hosts entries for valid domains after DNS has propogated so that you know your site is actually working properly.
