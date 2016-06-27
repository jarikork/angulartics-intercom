## angulartics-intercom

Intercom plugin for [Angulartics](https://github.com/angulartics/angulartics).

## Install

First make sure you've read installation and setup instructions for [Angulartics](https://github.com/angulartics/angulartics#install).

Then you can install this package either with `npm` or with `bower`.

### npm

```shell
npm install angulartics-intercom
```

Then add `angulartics.intercom` as a dependency for your app:

```javascript
require('angulartics')

angular.module('myApp', [
  'angulartics',
  require('angulartics-intercom')
]);
```

> Please note that core Angulartics doesn't export the name yet, but it will once we move it into [the new organization](http://github.com/angulartics).

### bower

```shell
bower install angulartics-intercom
```

Add the `<script>` to your `index.html`:

```html
<script src="/bower_components/angulartics-intercom/dist/angulartics-intercom.min.js"></script>
```

Then add `angulartics.intercom` as a dependency for your app:

```javascript
angular.module('myApp', [
  'angulartics',
  'angulartics.intercom'
]);
```

## Documentation

Documentation is available on the [Angulartics site](http://angulartics.github.io/).

### Settings

You can set an option to only send to Intercom if an attribute is present on the element. This is required because of the event throttling (500 - 1000/minute).

```javascript
angular
  .module('myApp', [])
  .config(function ($analyticsProvider) {
    $analyticsProvider.settings.intercomRequiresAttribute = true;
  });
```

When this is set an event will only be sent if an `analytics-intercom` attribute is on the element reporting the event. E.g.:

```html
<button ng-click="doTheThing()" analytics-on analytics-category="Thing" analytics-event="Was Done" analytics-intercom>DO THE THING</button>
```

## Development

```shell
npm run build
```

## License

[MIT](LICENSE)
