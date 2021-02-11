# Improve/Kickbox Sanity Check Action


This action runs the default set of E2E tests against a running kickbox/improve.

Usage example to run against production environment:

```yaml
steps:
  - uses: ngti/improve-sanity-action@master
    with:
      sanity-secrets: ${{ secrets.SANITY_SECRETS }}
      api-base-url: http://api-improve-location
      app-base-url: http://app-improve-location
      admin-base-url: http://admin-improve-location
```

Usage example to run against staging (as the urls have staging values as default, there is no need to pass anything in this case):

```yaml
steps:
  - uses: ngti/improve-sanity-action@master
    with:
      sanity-secrets: ${{ secrets.SANITY_SECRETS }}
```


Usage example with all inputs:

```yaml
steps:
  - uses: ngti/improve-sanity-action@master
    with:
      sanity-secrets: ${{ secrets.SANITY_SECRETS }}
      api-base-url: http://api-improve-location
      app-base-url: http://app-improve-location
      admin-base-url: http://admin-improve-location
      selenium-image: image-location
      continue-if-failed: false
      results-path: /tmp/reports
```

The action outputs `sanity-failed` with `1` if the tests didn't pass.
