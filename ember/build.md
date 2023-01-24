# Ember - Building applications

## Fingerprinting
Fingerprinting is the process of hashing assets during the build process so that browsers will recognize them as new, thus not using their cache.
Ember-CLI automatically hashes assets when building for production.

Fingerprinting can be configured like os:
```js
// ember-cli-build.ds
const EmberApp = require('ember-cli/lib/broccoli/ember-app');

module.exports = function (defaults) {
  const app = new EmberApp(defaults, {
    fingerprint: {
      // Enable fingerprinting for another production and integration environments
      enabled:
        process.env.EMBER_ENV === 'production' ||
        process.env.EMBER_ENV === 'integration',
      // Exclude a specific folder from fingerprinting
      exclude: ['images'],
    },
  });
```

- https://cli.emberjs.com/release/advanced-use/asset-compilation/
