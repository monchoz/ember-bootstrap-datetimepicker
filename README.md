# Ember-bootstrap-datetimepicker [![Build Status](https://travis-ci.org/plusacht/ember-bootstrap-datetimepicker.svg)](https://travis-ci.org/plusacht/ember-bootstrap-datetimepicker)

Datetimepicker add-on for ember-cli


## Installation ##

```bash
ember install ember-bootstrap-datetimepicker
```

Generate blueprints
```bash
ember generate ember-bootstrap-datetimepicker
```

## Basic Usage

### Template
```handlebars
{{bs-datetimepicker date=mydate format='YYYY-MM-DD'}}
```

### Brocfile.js ###
The twitter bootstrap resources will not be imported to your resources by default. If you want the add-on to add it you have to specify it in the `ember-cli-build.js`

```javascript
var app = new EmberApp(defaults, {
  'ember-bootstrap-datetimepicker': {
  "importBootstrapCSS": true,
  "importBootstrapJS": true,
  "importBootstrapTheme": true
  }
});
```

## Building yourself ##

Check out the demo on [github pages](http://plusacht.github.io/ember-bootstrap-datetimepicker "Bootstrap datetimepicker").
Alternatively you can clone this repo and run the app

```bash
sudo npm install -g ember-cli
git clone https://github.com/plusacht/ember-bootstrap-datetimepicker.git
cd ember-bootstrap-datetimepicker
npm install; bower install
ember serve
```
* Visit your app at http://localhost:4200.

## General Options ##
All options supported offered by [bootstrap-datetimepicker](http://eonasdan.github.io/bootstrap-datetimepicker/ "eonasdan's Bootstrap datetimepicker") are supported

## Bound Options ##

### date ###
Type: `Date`

This variable will be changed when the user changes the date and on the other side it will update the datetime picker when "date" is updated

### minDate ###
Type: `Date`

When you change this variable the component trigger an update to the minDate on the jQuery plugin.

### maxDate ###
Type: `Date`

When you change this variable the component trigger an update to the maxDate on the jQuery plugin.

### disabledDates ###
Type: `Date`

When you change this variable the component trigger an update to the disabledDates on the jQuery plugin.

### enabledDates ###
Type: `Array Date`

When you change this variable the component trigger an update to the enabledDates on the jQuery plugin.

## Usage ##

### Min / Maxdate example ###
Define your model

```javascript
var App.DateExample = Ember.Object.create({
  date1: moment(),
  mindate: moment("2014-11-01"),
  maxdate: moment("2015-12-01"),
  disabled:true});
}
```

Add the component to your template and bind the model.mindate with the component's minDate.

```handlebars
{{bs-datetimepicker date=date1 minDate=mindate maxDate=maxdate}}
```

Change minDate so the jquery plugin will be updated with the minDate value

```javascript
App.DateExample.set('maxdate', moment("2015-03-01"));
```

## Ember Compatibility ##

**0.4.0 - 0.4.1**
* 1.11.3
* 1.12.1
* 1.13.3


## Credits ##

This add-on is based on [bootstrap-datetimepicker](http://eonasdan.github.io/bootstrap-datetimepicker/ "eonasdan's Bootstrap datetimepicker")

And [plusacht/ember-bootstrap-datetimepicker](https://github.com/plusacht/ember-bootstrap-datetimepicker)
