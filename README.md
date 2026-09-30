# Opening Hand data

Shared Data for the Opening Hand app: card Legality, Card Kinds, Card Groups and the Archetype list. The app downloads `shared_data.json` from here once a day.

Don't edit it by hand. It's built by `tool/build_shared_data.dart` in the app project and published with `tool/publish_shared_data.sh`.

## Web pages

Also served with GitHub Pages (Settings → Pages → Deploy from branch `main`, folder `/`):

- `privacy/`: the privacy policy.
- `delete-account/`: deleting an Account outside the app, which Google Play requires. It uses the same public Supabase values as the app.
