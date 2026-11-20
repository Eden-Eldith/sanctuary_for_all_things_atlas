---
{"dg-publish":true,"dg-permalink":"index-internet","permalink":"/index-internet/","title":"Index-Internet","tags":["IndependentResearch","AI","DigitalGarden"],"created":"2026-11-19T10:26:48.294+00:00","updated":"2026-11-19T10:26:34.588+00:00","dg-note-properties":{"title":"Index-Internet","description":"How to recognise the Eldith Cognitive Systems research crawler and ask P.C. O'Brien to change what it visits.","date":"2026-11-19","tags":["IndependentResearch","AI","DigitalGarden"]}}
---

# Index-Internet

If `Index-Internet` appears in your server logs, it’s my research crawler. I’m P.C. O’Brien (Eden Eldith), the researcher behind [[Home\|Eldith Cognitive Systems]]. If you want me to stop visiting your site, email me with the domain or the affected URLs. [pcobrien@hotmail.co.uk](mailto:pcobrien@hotmail.co.uk)

## Why I built it

I wanted to be able to come back to a source months after an investigation and see how I found it. Index-Internet lets me keep a searchable copy of public pages, the links they contained and the time I collected them. I run the index myself. I may also use material from it in future model training or knowledge systems.

## What you’ll see in your logs

The crawler sends this `User-Agent` with its requests.

```text
Index-Internet/1.0 (+https://garden-backend-three.vercel.app/index-internet/)
```

It also sends my public email address in the HTTP `From` header.

It checks `/robots.txt` before fetching pages, including when a redirect points it to another site. A crawl makes one request at a time and normally waits at least two seconds between requests to the same host. You can ask for a longer interval with `Crawl-delay` in seconds.

## Controlling visits

To keep the crawler off your site, add this group to your `/robots.txt` file.

```text
User-agent: Index-Internet
Disallow: /
```

To exclude one section, use its path in the same group. For example, `Disallow: /forum/` excludes everything under `/forum/`.

The crawler uses the group for `Index-Internet`, or the `*` group if there’s no group for it. In that group, `Content-Signal: ai-train=no` or `Content-Usage: train-ai=n` tells it to skip the whole site. A rule such as `Content-Signal: /blog/ ai-train=no` tells it to skip that path. It caches robots rules for up to 24 hours.

## Questions about a request

You’re welcome to ask about a visit, request a slower pace or ask me to remove material I’ve already collected. A domain or URL is enough to start. If you’re asking about a particular request, its time and timezone will help me find it. [Email P.C. O’Brien](mailto:pcobrien@hotmail.co.uk)
