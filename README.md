# Improve/Kickbox Sanity Check Action

This action runs the default set of E2E tests against a running kickbox/improve.

Usage example given all the inputs:

```yaml
steps:
  - uses: ngti/improve-sanity-action@master
    with:
      sanity-secrets: ${{ secrets.SANITY_SECRETS }}
      api-base-url: http://api-improve-location
      app-base-url: http://app-improve-location
      admin-base-url: http://admin-improve-location
      selenium-image: image-location
      continue-if-failed: true (default false)
      results-path: path/to/reports (default /tmp/reports)
      suite: The test suite. Default: RunAll.xml
```

The action outputs `sanity-failed` with `1` if the tests didn't pass.
