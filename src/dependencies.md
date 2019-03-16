## Dependencies

<img width="100" align="right" style="margin: 0ex 1em" src="img/dependencies.jpg">
Source executed via Replete can depend on other bootstrapped-compatible libraries. To do so, the library must be bundled in Replete. (There is no facility to download dependencies into Replete.)

### Bundled Deps

Replete ships with many of the deps that are available to conventional ClojureScript code. In particular this includes [most of the Google Closure library](gcl.html) as well as these namespaces:

* `cljs.test`
* `clojure.core.reducers`
* `clojure.data`
* `clojure.template`
* `clojure.string`
* `clojure.set`
* `clojure.walk`
* `clojure.zip`

In addition, Replete ships with these libraries:

* [Fipp](https://github.com/brandonbloom/fipp) 0.6.14
* [transit-cljs](https://github.com/cognitect/transit-cljs) 0.8.248
