# ng-parallaxer

[AngularJS](http://angularjs.org/) directive for creating a parallax scrolling effect.

## How to use it

You must include the `ng-parallaxer` dependency on your angular module:
```
var app = angular.module("demoapp", ['ng-parallaxer']);
```

After that you can use the `ng-plx-root` and `ng-plx-layer` directives in your angular templates.

## Example Usage

```html
<div class="parallax" ng-app="demoapp" ng-plx-root>
	<div class="layer" id="layer-1"></div>
	<div class="layer" id="layer-2" ng-plx-layer ng-plx-x="5" ng-plx-y="5"></div>
	<div class="layer" id="layer-2" ng-plx-layer ng-plx-x="20" ng-plx-y="20"></div>
</div>
```

```css
.parallax {
	position: relative;
	width: 500px;
	height: 200px;
}

.parallax .layer {
	position: absolute;
	top: 0; left: 0; right: 0; bottom: 0;
	mouse-events: none;
	background-size: 100%;
	background-position: center center;
	backround-repeat: no-repeat;
}

#layer-1 {
	background-image: url(...);
}

#layer-2 {
	top: -5px; right: -5px; bottom: -5px; left: -5px;
	background-image: url(...);
}

#layer-3 {
	top: -5px; right: -20px; bottom: -20px; left: -20px;
	background-image: url(...);
}
```

## Other Examples:

* [9 Layer Example](http://codepen.io/32bitkid/full/EaQvOr/)

## Todo

- [ ] Throttle resize listener
- [ ] Exact `requestAnimationFrame` polyfill into module
- [ ] Make the `mouse-events: none` requirement optional
- [ ] Optimize the rendering loop; make it not render if target has been reached and nothing has changed.
