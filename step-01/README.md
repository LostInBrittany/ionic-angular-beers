#  Ionic Angular Beers tutorial - Step 01

This is the initial step of the tutorial.  In this step you will install Ionic, create an empty application and test it in your browser
and eventually in your Android phone.

## Installing Ionic

First, install [NodeJS](http://nodejs.org). Then use `npm` to install [Apache Cordova](https://cordova.apache.org/) and  [Ionic](/http://ionicframework.com/):

```
npm install -g cordova
npm install -g ionic
```

Verify that both tools work by calling them on the command line:

```
$ cordova -v
5.4.1

$ ionic -v
1.7.10
```

## Create an empty Ionic application

To create an empty application in `app` folder, you simply do:

```
$ ionic start app blank
```

Then you can go to the `app` folder and test your new application by using `ionic serve`:

```
$ ionic serve
```

The `ionic serve` runs a web server on  `http://localhost:8100/` serving the Ionic application in web mode.

![Application on browser](../img/step-01-01.png)

## Adding Android support

In order to add Android support you need to have Android build tools (SDK, platform tools, emulator...) in your computer.
The easiest way to do it is installing [Android Studio](http://developer.android.com/sdk/index.html).

To add Android support you do:

```
$ ionic platform add android
$ ionic build android
$ ionic emulate android
```

![Application on Android emulator](../img/step-01-02.png)

## Structure of the application

Here is what the outer structure of your Ionic project will look like:

```
├── bower.json     // bower dependencies
├── config.xml     // cordova configuration
├── gulpfile.js    // gulp tasks
├── hooks          // custom cordova hooks to execute on specific commands
├── ionic.project  // ionic configuration
├── package.json   // node dependencies
├── platforms      // iOS/Android specific builds will reside here
├── plugins        // where your cordova/ionic plugins will be installed
├── scss           // scss code, which will output to www/css/
└── www            // application - JS code and libs, CSS, images, etc.
```

Since every Ionic app is basically a web page, the `index.html` file in our app which defines the first page that loads in the app.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no, width=device-width">
    <title></title>

    <link href="lib/ionic/css/ionic.css" rel="stylesheet">
    <link href="css/style.css" rel="stylesheet">

    <!-- IF using Sass (run gulp sass first), then uncomment below and remove the CSS includes above
    <link href="css/ionic.app.css" rel="stylesheet">
    -->

    <!-- ionic/angularjs js -->
    <script src="lib/ionic/js/ionic.bundle.js"></script>

    <!-- cordova script (this will be a 404 during development) -->
    <script src="cordova.js"></script>

    <!-- your app's js -->
    <script src="js/app.js"></script>
  </head>
  <body ng-app="starter">

    <ion-pane>
      <ion-header-bar class="bar-stable">
        <h1 class="title">Ionic Blank Starter</h1>
      </ion-header-bar>
      <ion-content>
      </ion-content>
    </ion-pane>
  </body>
</html>
```

In the shell above, we are including the Ionic CSS and both the core Ionic JS and the Ionic AngularJS extensions in the `ionic.bundle.js` file. Ionic comes with `ngAnimate` and `ngSanitize` bundled in, but to use other Angular modules you’ll need to include them from the `lib/js/angular` directory.

Also note that the `cordova.js` or `phonegap.js` file must be the last script, and that this file will not be found in your development files, but rather automatically included when running or emulating your app.

## Summary ##

Now that you have created an empty application, go to [step 2](../step-02) to learn about adding some AngularJS elements to our application.
