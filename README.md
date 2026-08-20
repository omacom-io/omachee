# omachee.org

A Cloudflare Worker serving one static page for `omachee.org`, a common
misspelling of [omarchy.org](https://omarchy.org):

> Yes, it's pronounced OMACHEE, but we spell it OMARCHY. The R is silent.

Colors and type are lifted from omarchy.org's `root.css` (Tokyo Night,
JetBrains Mono).

## Deploying

```sh
npx wrangler deploy
```

Routes `omachee.org/*` and `*.omachee.org/*` are declared in `wrangler.jsonc`.
DNS is two proxied `A` records pointing at `192.0.2.1` — a placeholder, since
the Worker intercepts at the edge and no origin is ever contacted.

Unmatched paths serve the same page rather than a 404, so mistyped deep links
still land on the joke.
