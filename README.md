# ionic-ssr-bug
Repository for [Ionic Issue 21203](https://github.com/ionic-team/ionic/issues/21203). 

How to reproduce the bug:

**1) Working version:**

-npm install

-npm run prerender

Result SUCCESS:
```
Prerendering 2 route(s) to C:\_GIT\Examples\ionic-ssr-bug\www\browser
AppComponent constructor
AppComponent constructor
platform ready
HomePage constructor
platform ready
CREATE C:\_GIT\Examples\ionic-ssr-bug\www\browser\page1\index.html (35547 bytes)
CREATE C:\_GIT\Examples\ionic-ssr-bug\www\browser\index.html (40978 bytes)
```

**2) Introduce bug:**

ng update @ionic/angular

-->  Updating package.json with dependency @ionic/angular @ "5.1.0" (was "5.0.5")...

-result:
```
Prerendering 2 route(s) to C:\_GIT\Examples\ionic-ssr-bug\www\browser
AppComponent constructor
platform ready
AppComponent constructor
HomePage constructor
TypeError: Cannot read property 'width' of undefined
    at Device (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:116738:36)
    at hydrateAppClosure (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:116827:2)
    at hydrateFactory (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:120408:3)
    at render (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:121793:9)
    at resolve (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:121754:17)
    at new ZoneAwarePromise (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:123284:33)
    at hydrateDocument (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:121733:12)
    at C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:73174:91
    at applicationRef.isStable.pipe.toPromise.then (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:67245:48)
    at ZoneDelegate.invoke (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:122765:30)
platform ready
CREATE C:\_GIT\Examples\ionic-ssr-bug\www\browser\page1\index.html (2812 bytes)
TypeError: Cannot read property 'width' of undefined
    at Device (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:116738:36)
    at hydrateAppClosure (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:116827:2)
    at hydrateFactory (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:120408:3)
    at render (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:121793:9)
    at resolve (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:121754:17)
    at new ZoneAwarePromise (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:123284:33)
    at hydrateDocument (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:121733:12)
    at C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:73174:91
    at applicationRef.isStable.pipe.toPromise.then (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:67245:48)
    at ZoneDelegate.invoke (C:\_GIT\Examples\ionic-ssr-bug\www\server\main.js:122765:30)
```
