# ng-ovh-timeline

> An Angular.js directive that generates a responsive, data-driven vertical timeline to tell a story, show history or describe a sequence of events.

[![Downloads](https://badgen.net/npm/dt/@ovh-ux/ng-ovh-timeline)](https://npmjs.com/package/@ovh-ux/ng-ovh-timeline)[![Dependencies](https://badgen.net/david/dep/ovh-ux/ng-ovh-timeline)](https://npmjs.com/package/@ovh-ux/ng-ovh-timeline?activeTab=dependencies)[![Dev Dependencies](https://badgen.net/david/dev/ovh-ux/ng-ovh-timeline)](https://npmjs.com/package/@ovh-ux/ng-ovh-timeline?activeTab=dependencies)[![Gitter](https://badgen.net/badge/gitter/ovh-ux/blue?icon=gitter)](https://gitter.im/ovh/ux)

## Install

```sh
yarn add @ovh-ux/ng-ovh-timeline
```

## Usage

```js
import angular from 'angular';
import ngOvhTimeline from '@ovh-ux/ng-ovh-timeline';

angular
  .module('myApp', [
    ngOvhTimeline,
  ]);
```

To define a timeline, do the following (either manually or using ng-repeat on a dataset.

```javascript

  // in controller
  $scope.events = [{
    badgeClass: 'info',
    badgeIconClass: 'glyphicon-check',
    title: 'First heading',
    content: 'Some awesome content.'
  }, {
    badgeClass: 'warning',
    badgeIconClass: 'glyphicon-credit-card',
    title: 'Second heading',
    content: 'More awesome content.'
  }];
```

```html

  <!-- view -->
  <timeline-event ng-repeat="event in events">
    <timeline-badge class="{{event.badgeClass}}">
      <i class="glyphicon {{event.badgeIconClass}}"></i>
    </timeline-badge>
    <timeline-panel class="{{event.badgeClass}}">
      <timeline-heading>
        <h4>{{event.title}}</h4>
      </timeline-heading>
      <p>{{event.content}}</p>
    </timeline-panel>
  </timeline-event>
```
There is a bit of markup here but `<timeline-heading>` is optional.
`<timeline-badge>` is for the centre line between the two sides, and should represent the event type that occured.

## Test

```sh
yarn test
```

## Related

- Panels are now designed to float left, then right, side to side.  Float right is forced on smaller (eg. mobile) devices.

- If you define the events in an array and have HTML content to output, use `ng-bind-html={{event.attribute}}` and require the `ngSanitize` module.

- If you are using Bootstrap 3 it affects the timeline CSS, so include `timeline-bootstrap.[css|less]}` to re-adjust the offsets.

- If you want use animation when timeline events scroll into view, include [angular-scroll-animate](https://github.com/rpocklin/angular-scroll-animate) and import `timeline-animations.[css|less]}`.

## Contributing

Always feel free to help out! Whether it's [filing bugs and feature requests](https://github.com/ovh-ux/ng-ovh-timeline/issues/new) or working on some of the [open issues](https://github.com/ovh-ux/ng-ovh-timeline/issues), our [contributing guide](CONTRIBUTING.md) will help get you started.

## License

[BSD-3-Clause](LICENSE) © OVH SAS
