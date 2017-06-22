# Angular Timeline

![githubbanner](https://user-images.githubusercontent.com/3379410/27423240-3f944bc4-5731-11e7-87bb-3ff603aff8a7.png)

[![Maintenance](https://img.shields.io/maintenance/yes/2017.svg)]() [![Chat on gitter](https://img.shields.io/gitter/room/ovh/ux.svg)](https://gitter.im/ovh/ux)

[![NPM](https://nodei.co/npm/ovh-angular-timeline.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/ovh-angular-timeline/)

This is a fork of the original component from version 1.5.0

This forked version add options to the directive to manage the layout of the timeline

An Angular.js directive that generates a responsive, data-driven vertical timeline to tell a story,
show history or describe a sequence of events.

# Demo

[Demo](http://rpocklin.github.io/angular-timeline/example/index.html)

[Demo without bootstrap](http://rpocklin.github.io/angular-timeline/example/index-no-bootstrap.html)

[Original Implementation (HTML / Javascript)](http://bootsnipp.com/snippets/featured/timeline-responsive)


# Inspiration
[1](http://bootsnipp.com/snippets/featured/two-column-timeline-not-responsive)
[2](http://bootsnipp.com/snippets/featured/timeline-single-column)
[3](http://bootsnipp.com/snippets/featured/single-column-timeline)
[4](http://bootsnipp.com/snippets/featured/timeline-with-images-and-tooltip)
[5](http://bootsnipp.com/snippets/featured/timeline-dotted)
[6](http://codyhouse.co/demo/vertical-timeline/index.html)

## Installation

1. Install the plugin into your Angular.js project, manually or via

  `bower install ovh-angular-timeline --save`

1. Include `ovh-angular-timeline.css` in your app:

  `<link rel="stylesheet" href="bower_components/ovh-angular-timeline/dist/ovh-angular-timeline.css"/>`

1. Include `ovh-angular-timeline.js` in your app:

  `<script src="bower_components/ovh-angular-timeline/dist/ovh-angular-timeline.js"></script>`

1. Add `ovh-angular-timeline` as a new module dependency in your angular app.

  `var myapp = angular.module('myapp', ['ovh-angular-timeline']);`

1. To define a timeline, do the following (either manually or using ng-repeat on a dataset):

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

## Notes

- The demo uses [angular-scroll-animate](https://github.com/rpocklin/angular-scroll-animate) to trigger CSS animations when timeline events scroll into view.  It's totally optional to include this or not and is just there for effect.

- Panels are now designed to float left, then right, side to side.  Float right is forced on smaller (eg. mobile) devices.
- If you define the events in an array and have HTML content to output, use `ng-bind-html={{event.attribute}}` and require the `ngSanitize` module.

- You can use either the SASS styles directly file under `/dist` or the compiled CSS files, up to you :)

- If you are using Bootstrap 3 it affects the timeline CSS, so include `ovh-angular-timeline-bootstrap.[css|scss]}` to re-adjust the offsets e.g:

```html
  <link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.css" />
  <link rel="stylesheet" href="bower_components/ovh-angular-timeline/dist/ovh-angular-timeline-bootstrap.css" />
  <script src="bower_components/ovh-angular-timeline/dist/ovh-angular-timeline.js"></script>
```


## Running Locally

1. Checkout git repository locally: `git clone ovh-angular-timeline.git`
1. `npm install`
1. `bower install`
1. `grunt serve`
1. View `http://localhost:9000/example/` in your browser to see the example.


## Contributing

1. Fork it
1. Create your feature branch (`git checkout -b my-new-feature`)
1. Beautify (`grunt beautify`)
1. Ensure it passes code-checks / tests (`grunt`)
1. Commit your changes (`git commit -am 'Added some feature'`)
1. Push to the branch (`git push origin my-new-feature`)
1. Create a new Pull Request


## History

* 1.5.2 Updated dependency used in example `angular-scroll-animate` from 0.8.0 to 0.9.1.
* 1.5.0 Updated dependencies, simplified nested components and improved example.  Changed `timeline-node` to `timeline-event`. Removed `replace = true` in directives.
* 1.2.1 Cleaned up dependencies and build steps.
* 1.2.0 Updated example and styling to be more responsive.
* 1.0.0 Initial release


## TODO

- Add some tests

## Thanks
*luisrudge* for the original vanilla JS implementation on [Bootsnipp](http://bootsnipp.com/snippets/featured/timeline-responsive)


## License

Released under the MIT License. See the [LICENSE][license] file for further details.

[license]: https://github.com/ovh-ux/ovh-angular-timeline/blob/master/LICENSE
