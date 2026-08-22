# I helped my client generate $430k CAD in quotations, save 10+ weekly hrs and $500/yr in hosting fees

I've recently been working with Johnny Loprete from Master Sealer. [Master Sealer](https://www.mastersealer.com) is a landscaping SMB (small business) based in Vaughan, Canada.

They reached out to me to solve a number of issues:
- **wasting hours each week** doing things manually that a machine can do faster and more accurately
- fixing issues with email deliverability, leading to **$430k CAD** of quotations that would've otherwise landed in spam

I was able to help them streamline much of their workflow. While working with them, I also found ways to save them money in their tech stack. I suggested a few solutions, and nobody says no to cost savings, so we implemented those as well.

In short, I helped mastersealer to:
- save **10+ weekly hrs** on quotations and invoicing
- improve mail deliverability by **50.61%** (leading to **$430k CAD** of quotations that would've otherwise landed in spam)
- save **$500/yr** on hosting fees
- fix numerous security and mailing issues in their DNS records

Here's a breakdown of exactly what I built for Master Sealer, and the business outcomes I produced.

## Custom Quotation software for automating customer quotations

Before I started, Johnny was spending hours manually writing quotations and making PDFs out of them, and then emailing them to prospects. Every single step in that chain can be done by a machine. 

![flow chart showing the manual steps johnny had to do before i automated the entire workflow for him](https://www.hassandev.me/images/case-studies/mastersealer/manual-quotation-workflow.webp)

So I proposed an automated system to help with that.

I built a custom web app in Django that lets Johnny fill in customer information in a simple and quick form. The app then compiles that information into a branded PDF template, and emails it to the customer. The app also automatically tracks useful stats for Johnny to review later.

## 50.61% Deliverability improvements with Google Workspace, worth $430,388.75 in quotations

Mastersealer had frequent issues with emails to Hotmail/Outlook and Yahoo mail not landing in users' inboxes. They'd frequently end up in the spam folder.

I proposed to migrate emails to Google Workspace and take advantage of Google's reputation to help improve mail deliverability. **I handled the entire migration process**, and also fixed many issues in the mastersealer.com DNS records that were preventing emails from successfully reaching users' inboxes.

I checked the stats, and this one change *(along with fixing DNS records)* improved their mail deliverability by **50.61%**, and helped send quotations worth **$430,388.75** to customers just in the **last three months**. Imagine the revenue this business generates now just because I fixed their email deliverability issues.

![CLI report showing mail deliverability improvement and revenue growth after implementing my changes](https://www.hassandev.me/images/case-studies/mastersealer/deliverability-and-revenue-improvements.webp)

I redacted information like B2B clients and used estimated revenue numbers to protect client anonymity.

## Migrating from AWS to save $500/yr in hosting fees

Mastersealer was previously hosting the internal quotation app on an AWS EC2 instance. There were several problems with this:
1. This is an internal business app, only used certain times of the day when Johnny is sending quotations. But the EC2 instance was live 24/7, costing money by the hour.
2. All our data was stored in a separate DB, and mails are sent via SMTP. There was no need to have a dedicated server. 
3. The business is seasonal, and doesn't run for 3-4 months, so having an unused running VPS all year round was a huge waste.

**Just the AWS hosting alone was costing Johnny $500/yr.**

![aws transaction history showing $500/yr hosting costs](https://www.hassandev.me/images/case-studies/mastersealer/aws-billing-history.webp)

I proposed moving to a serverless solution like Vercel. 

I had to go through some challenges to make the app work on a serverless platform, particularly the **PDF template generation**. It's actually quite difficult to create PDFs on a serverless platform when it doesn't allow you to install the required system packages. :)

But I made it work. And luckily, internal tools like these that don't get heavy usage easily fall under Vercel's free tier. So, Master Sealer now saves $500/yr by simply migrating from AWS to Vercel.

> **Fun fact**
> 
> Vercel actually uses AWS under-the-hood. But since they're using a serverless architecture, they don't incur as much cost, and they can offer generous free tiers.

## DNS Records cleanup, security patches, and deliverability improvements

The mastersealer.com domain had numerous DNS record issues. This was causing major problems with email deliverability, among other things. It was actually tech support from Nexcess (a hosting provider) that caused all these issues. 

In Johnny's own words:

![whatsapp chat screenshot showing johnny telling me how bad nexcess tech support is](https://www.hassandev.me/images/case-studies/mastersealer/nexcess-tech-support-discussion.webp)

> **Key Takeaway**
> 
> It really just goes to show you why it's always a good idea to have a dedicated guy on your team who can handle technical things like these. If you want someone who actually cares about your product and isn't just trying to make a quick buck, you should really book a call with me. 
> 
> Johnny's just one of many clients who have been working with me for many years now because they understand I'm with them when things break.

In no particular order, the DNS issues with mastersealer.com:

1. No `CAA` records (for SSL certificates) and `DMARC` records (for spam prevention)
2. Typos in `MX` records: `smtp.goggle.com` instead of `smtp.google.com` routing inbound emails to a typo domain.
3. `DKIM` keys set on subdomains instead of root domains: `www.mastersealer.com` instead of `mastersealer.com`.
4. `DKIM` clutter from multiple conflicting providers: MailerLite, MailChimp, and Amazon SES.
5. Malformed SRV records: Missing protocol prefixes and priority/weight formatting in the records.
6. Duplicate SPF includes. Same SPF records listed twice.
7. Public FTP and SSH `CNAME` records which exposed direct server IP.
8. Weak DMARC policies that offered zero spoofing protection.

I fixed each and every one of them. After fixing these issues, not only was the email deliverability improved, but many security vulnerabilities were also patched.

## Conclusion

So, I got hired to fix email deliverability issues and streamline some repetitive tasks.

I ended up achieving a lot more:
- saving **10+ weekly hrs** on quotations and invoicing
- improving mail deliverability by **50.61%** (leading to **$430k CAD** of quotations that would've otherwise landed in spam)
- saving **$500/yr** on hosting fees
- fixing numerous security and mailing issues in their DNS records

## Wanna get in touch?

If you're looking for a developer who can help you achieve similar results, whether that's building custom software, AI automations, mobile apps, or anything else, I'm your guy.

Book a call with me right now, and let me help you take your business to the next level.

[**Book a free call**](https://calendly.com/itshassanaziz/discuss-a-project)

---

[Website](https://www.hassandev.me) • [Twitter / X](https://x.com/intent/user?screen_name=nothassanaziz) • [LinkedIn](https://www.linkedin.com/in/hassan-aziz-web) • [GitHub](https://github.com/hassanaziz0012)
