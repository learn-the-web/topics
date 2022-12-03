---
title: "Domains & DNS"
tags: "domains dns tld ca com internet web ip works a ns mx cname email hover fastmail github cloudflare apex"
desc: "Understanding domains and the DNS system and setting up a custom domain for your website."
playlist: domains
extra_practice:
  week:
    title: "Web Dev 5, Week 03"
    url: "/courses/web-dev-5/week-03/"
  slides:
    - title: "Domains & DNS"
      url: "/courses/web-dev-5/domains-dns/"
    - title: "Email account types"
      url: "/courses/web-dev-5/email-account-types/"
  lessons:
    - title: "Buying a domain & email"
      url: "/courses/web-dev-5/buying-domain-hosting-setup/"
    - title: "Hosting setup"
      url: "/courses/web-dev-5/hosting-setup/"
  activities:
    - title: "Domain Destroyer"
      url: "domain-destroyer"
---

The Internet is a distributed system of interconnected computers throughout the world.

Each computer as an address, know as an IP Address, but mostly humans want something more memorable—that’s where domains come in.

---

## Domains & IPs

Domains, like `google.com` or `learntheweb.courses`, are just for humans so we can more easily remember where a website is.

But computers don’t necessarily care about domains, they care about IP address, which are the actual locations/names of the computers connected to The Internet. _Every single computer connected to the Internet has a unique IP address._

An IP address looks something like this: `192.168.1.0` or `2001:0db8:85a3:0000:0000:8a2e:0370:7334`—which aren’t terribly memorable for regular mortals. Whereas, domains like `github.com` are much more memorable.

So the purpose of the Domain Name System (DNS) is to map domains to IP address and provide other information about a website.

A simple example of DNS records might look like this:

```
learntheweb.courses.        A    192.168.0.1
mail.learntheweb.courses.   MX   192.168.0.2
```

There’s a direct connection between a domain and it’s associated IP address.

---

## How everything connects together

![](domains-dns-servers.png)

### How you see a website

After you type the domain into your browser and go your computer starts making a bunch of really quick requests (less than 100 ms):

1. Your computer connects to a DNS server, requesting DNS information for the domain you typed in.
   Your computer already knows the IP address to at least one DNS server because your Internet provider sent it to your computer.
2. The DNS will then send back the IP address of the computer that hosts the website to your computer, if it knows it.
   If it doesn’t know the IP address it will send your computer the IP address of another name server that might know.
   The loop continues until your computer has the IP address of the host.
   **IP address of the website host is called the `A` record.**
3. When your computer gets the IP address it connects directly to the host computer and requests to see the website.
4. The host/web-server will then return the `index.html` file for the website you requested.
   Your browser will then start requesting all the other resources of your website like CSS, images, JavaScript, etc.
   If those resources are located on another domain the whole process starts all over again at step 1.

#### Authoritative name server

The `NS` records in your DNS information points to the primary name server for your domain—usually your registrar.

All the domain servers synchronize with each other so it can take time for your domain records to show up on all the DNS servers around the world.

If the DNS server your browser requests doesn’t know the IP for the domain you want, or if that information has expired, your computer will most likely connect to the authoritative name server for your domain to get the real, fresh DNS information.

### How e-mails are sent

The process for sending e-mails is similar to viewing a website but requires more requests and more DNS records.

**The DNS records for e-mail servers are called the `MX` records.**

After you write your e-mail message and click send a whole bunch of requests are sent out again:

1. Your computer connects to a DNS to find the `A` record for your mail server.
2. The DNS sends back the IP for your e-mail server.
3. Your computer connects to your e-mail server using the new IP and submits a new message.
4. Your e-mail server then connects to the DNS to find the `MX` record for the domain of the person you’re sending your message to.
5. The `MX` record is sent back to your computer.
6. If the `MX` record isn’t an IP address a whole new DNS lookup must happen for the `A` record of the other mail server.
7. The DNS will then send back the IP address of the other person’s e-mail server.
8. Your e-mail server connects to the other person’s e-mail server and posts the new message on it.

---

## Purchasing and hooking up services

It’s usually a good idea to purchase your services from different providers (domains from registrars, hosting from hosts, e-mail from e-mail providers, etc.) for a few reasons:

- More control over your domain settings, e-mail addresses, etc.
- Easier to move hosts—because you will want to at some point. If you transfer your host, then you don’t also have to transfer your e-mails—and you won’t lose any messages. And you don’t have to transfer your domain, just point it to a new host.
- If you have hosting related problems, you may also have e-mail related problems if they’re in the same location.
- Security: if your hosting account is hacked, then so is your domain registrar and the hacker can just transfer your domain somewhere else.
- It’s not always clear who owns the domain when registering it with a host.

The only real downside of separating domains and hosting is a slight loss in convenience.

### Buying a domain on Hover

The first step in the whole process is buying a domain. I usually buy my domains from [Hover](https://hover.com/J2Frl31i)†.

Though we generally call it “buying” a domain you aren’t technically _buying_ it, but _leasing_ it for a certain amount of time, usually a year. _And every year you have to pay for it again._

[**☛ Follow the Hover setup lesson.**](/courses/web-dev-5/buying-domain-hosting-setup/)

### Buying e-mail service with FastMail

There are lots of different e-mail providers and hosts often provide e-mail exchange also. But it’s best to purchase your e-mail from another provider. I often buy my e-mail services from [FastMail](https://www.fastmail.com/?STKI=12009945)†.

_Make sure your e-mail provider supports custom domains—FastMail only supports this in their more expensive packages. ([The standard package works great!](https://www.fastmail.com/?STKI=12009945))†_

[**☛ Follow the FastMail setup lesson.**](/courses/web-dev-5/buying-an-email-address/)

### Hosting on GitHub

Using GitHub as a static web host is simple, integrates with our processes—and it’s free.

[**☛ Follow the hosting lesson.**](/courses/web-dev-1/website-on-github/)

---

## Video list

1. [Domains & DNS: How the web works](https://videos.learntheweb.courses/playlists/domains/#1-how-the-web-works)

## Supplemental links

### Articles

- [What really happens when you navigate to a URL](http://igoro.com/archive/what-really-happens-when-you-navigate-to-a-url/)
- [How Browsers Work](http://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)
- [How the Web Works](http://mkcohen.com/how-the-web-works-in-one-easy-lesson)

### DNS tools

- [MX Toolbox](http://mxtoolbox.com/)
- [Pingdom: DNS check tool](http://dnscheck.pingdom.com/)

### Recommended registrars

- [Hover](https://hover.com/J2Frl31i)†
- [Gandi](http://www.gandi.net/)

### Recommended e-mail providers

- [FastMail](https://www.fastmail.com/?STKI=12009945)†
- [Google Apps for Work](http://www.google.com/work/apps/business/)
- [Rackspace](http://www.rackspace.com/email-hosting/webmail/)
- [MailRoute](http://mailroute.net/) (strong spam protection)

### Recommended website hosts

- [GitHub](https://github.com/)
- [SiteGround](http://www.siteground.com/)
- [WiredTree](https://www.wiredtree.com/)
- [A Small Orange](http://asmallorange.com/)
- [DreamHost](https://www.dreamhost.com/)

### Security & performance

- [CloudFlare](https://www.cloudflare.com/)

---

_† The FastMail links are referral links, from me, that will get you 10% off your first year. The Hover links are referral links, from me, that will get you \$2 off your first domain._
