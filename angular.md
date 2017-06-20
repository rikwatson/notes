# Angular

 * End-2-end Testing with [Protractor](https://calebmcelrath.wordpress.com/2017/01/30/write-end-to-end-tests-for-your-angular-2-applications-with-protractor/)
 * [Angular 2 in the MEAN stack a project template](https://calebmcelrath.wordpress.com/2017/01/27/angular-2-in-the-mean-stack-a-project-template/)

_.c.f._

 * [React](./react.md)

# Upgrading

```bash
npm install @angular/{common,compiler,compiler-cli,core,forms,http,platform-browser,platform-browser-dynamic,platform-server,router,animations}@latest typescript@latest --save
```

Now upgrade all global packages.

```bash
npm update -g 
```

or

```bash
npm i -g npm
```

```
npm show {pkg} version
```

E.g.

```
npm show express version
```

```
npm install @angular/{common,compiler,compiler-cli,core,forms,http,platform-browser,platform-browser-dynamic,platform-server,router,animations}@latest typescript@latest --save
ng build --prod --aot
```

## Building

```bash
ng build --prod --aot
```

## Links

 * [top-8-resources-to-explore-angular-4](https://hackernoon.com/top-8-resources-to-explore-angular-4-ff2c1b42020a)
 * [Angular 4 Announcement](http://angularjs.blogspot.co.uk/2017/03/angular-400-now-available.html)
 * DI / Dependence Injection https://angular.io/docs/ts/latest/guide/dependency-injection.html https://angular-2-training-book.rangle.io/handout/di/angular2/inject_and_injectable.html https://blog.thoughtram.io/angular/2015/09/17/resolve-service-dependencies-in-angular-2.html
 * Browser Support https://angular.io/docs/ts/latest/guide/browser-support.html

## Performance Issues with Android

* http://stackoverflow.com/questions/29130227/angularjs-android-4-2-very-slow-to-react
* http://stackoverflow.com/questions/42963049/angular-2-app-is-very-slow-on-android-devices
* https://forum.ionicframework.com/t/android-performances-ionic2-angular-much-worse-than-ios/51438/9
* https://meta.discourse.org/t/the-state-of-javascript-on-android-in-2015-is-poor/33889
* https://eviltrout.com/2016/02/25/fixing-android-performance.html
* https://meta.discourse.org/t/a-tour-of-how-the-widget-virtual-dom-code-in-discourse-works/40347
* 
