# Opening Hand data

Shared Data for the Opening Hand app: card Legality, Card Kinds, Card Groups and the Archetype list. The app downloads `shared_data.json` from here once a day.

Don't edit it by hand. It's built by `tool/build_shared_data.dart` in the app project and published with `tool/publish_shared_data.sh`.

## Web pages

Also served with GitHub Pages on https://openinghand.app (Settings → Pages → Deploy from branch `main`, folder `/`):

- `index.html`: the landing page. `404.html`: page not found.

- `privacy/`: the privacy policy.
- `delete-account/`: deleting an Account outside the app, which Google Play requires. It uses the same public Supabase values as the app.
- `cancel-reset/`: cancelling a two-factor reset from the warning email.

All pages share `style.css`, the fonts in `assets/fonts/` (woff2, Latin only, with their OFL licences) and the logo files in `assets/logo/`. Nothing on the landing page loads from other servers.

### Changing the landing page

`index.html`, `404.html` and `style.css` are built from the app project's design files, so edit those and rebuild rather than editing here:

    python3 design/website/build-site.py        # in the OpeningHand project

The source is `design/website/template.html` (the approved mockup). The share image `og-image.png` is rendered from `design/website/og-image.html` (see the comment at its top).

### When the Play listing goes public

The download button is a "Coming soon to Google Play" pill in two places in `template.html` (`<p class="pill" role="note">`). Replace both with Google's official "Get it on Google Play" badge linking to the listing, following Google's badge guidelines, then rebuild. Google allows the badge only for a live listing.
