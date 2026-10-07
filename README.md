# sgsamy.com: move off GoDaddy Website Builder to free hosting

This folder is the complete website. It is hosted free on GitHub Pages; your only ongoing cost is the domain name.

Keep your GoDaddy site running until step 4 is done, so there is no downtime.

## 1. Put the files on GitHub (10 minutes)

1. Sign in to GitHub as **SGSAMY**.
2. Create a new **public** repository named exactly `sgsamy.github.io`.
3. On the new repo page, click **uploading an existing file**.
4. Drag in everything from this folder (all the `.html` files, `style.css`, `CNAME`, this README), then click **Commit changes**.
5. Go to **Settings → Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and Save.
6. Still on that page, under **Custom domain**, check it says `sgsamy.com` (the `CNAME` file sets this). Save if needed.

Within a minute or two the site is live at https://sgsamy.github.io.

## 2. Point sgsamy.com at GitHub (at GoDaddy, for now)

In GoDaddy, open **My Products → sgsamy.com → DNS**.

1. Delete any existing **A** record for `@` and any **CNAME** for `www`. If GoDaddy shows "Forwarding" or says the domain is connected to Websites + Marketing, disconnect that first.
2. Add four **A** records, Name `@`, one for each value:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
3. Add a **CNAME** record: Name `www`, Value `sgsamy.github.io`.

DNS changes usually take under an hour, occasionally up to 24 hours.

## 3. Turn on HTTPS

Back in GitHub **Settings → Pages**, wait until the DNS check shows green, then tick **Enforce HTTPS**. The certificate is free.

## 4. Cancel the GoDaddy website plan

Once https://sgsamy.com shows the new site:

- In GoDaddy, cancel (or turn off auto-renew for) **Websites + Marketing / Website Builder** and any add-ons such as SEO tools or extra SSL.
- **Do not cancel the domain sgsamy.com.**

## 5. Optional: move the domain to a cheaper registrar

Cloudflare Registrar sells .com renewals at cost with no markup (roughly £8–10 a year). Do this a month or two before the domain's next renewal date.

1. Create a free Cloudflare account and **Add a site** → `sgsamy.com` (Free plan). Check the DNS records it imports include the four A records and the `www` CNAME above (set them to "DNS only", grey cloud).
2. At GoDaddy, change the domain's nameservers to the two Cloudflare gives you.
3. At GoDaddy, **unlock** the domain and request the **authorisation (EPP) code**.
4. In Cloudflare, go to **Domain Registration → Transfer Domains**, enter the code and pay for the transfer (this includes one extra year).
5. Approve the transfer email from GoDaddy if asked.

A domain can only be transferred if it was registered or last transferred more than 60 days ago.

## Updating the site later

Edit the text in the `.html` file on GitHub (open the file, click the pencil icon, change it, Commit). The live site updates within a minute or two.

## Before you upload: check one link

On the GitHub Projects page, the **Marketing Mix Modelling** card links to your GitHub profile because its exact repository name wasn't known. To point it at the repo, open `github-projects.html`, find `Marketing Mix Modelling`, and change `https://github.com/SGSAMY` in that card to the repo's full address.

## Contact form

The old GoDaddy contact form is replaced by LinkedIn buttons, because GitHub Pages cannot send email by itself. If you want a form back, Formspree.io has a free plan; sign up, create a form, and it gives you a short snippet to paste into `index.html`.
