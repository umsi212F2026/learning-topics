# cache invalidation

Answer in two or three sentences, in your own words, with nothing open in front of you.

### q-invalidation-vs-reload

What is the difference between cache invalidation and reloading the page?

### q-invalidation-vs-redeploy

What is the difference between cache invalidation and a redeploy?

### q-invalidation-vs-busting

What is the difference between cache invalidation and cache busting?

### q-catch-new-address-invalidates

A site's frontend is on Pinecart. This is how its CDN behaves:

- **Pinecart** hosts a built frontend and serves it through its CDN.
  - Its CDN keeps a copy of each page for up to 12 hours. The setting "Clear CDN cache on deploy"
    is on for a new site; with it off, a deploy leaves the CDN's copies in place, and the deploy
    list says "CDN cache kept" beside that deploy. The Clear CDN cache button clears it at any time.
    A request for a page whose address differs, even only after a `?`, is fetched fresh from the
    latest deploy.

After a deploy that Pinecart's deploy list shows with "CDN cache kept" beside it, a student opens
the site and still sees the old version. They add `?v=2` to the end of the address, load it, and
see the new version.

The student says:

"There, I've invalidated the cache, so every visitor sees the new version now."

What is wrong with what they said?
