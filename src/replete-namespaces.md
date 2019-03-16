## Replete Namespaces

<img width="100" align="right" style="margin: 0ex 1em" src="img/replete-namespaces.jpg">
In order to make Replete more useful, some native I/O facilities have been added to the JavaScript engine running in Replete and these have been exposed via a few namespaces. To make things easier to use, the functions in these namespaces adhere fairly closely to existing Clojure / ClojureScript analogs.

The code for these namespaces is are always available—you just need to `require` them.

These namespaces comprise
* `replete.core`
* `replete.io`
* `replete.http`

To explore these namespaces, you can evaluate `(dir replete.core)`, for example, to see the symbols in `replete.core`, and then use `doc` to see the docs for any of the symbols.

Online documentation for the namespaces is available: [Replete SDK](sdk.html).

### replete.core

([Online docs](replete-core.html))

This namespace includes basic I/O capabilities like `slurp`, `spit` and `read-line`. The I/O facilities are expressed in protocols defined in `replete.core` modeled after those in Clojure, like `IReader`, `IOutputStream`, _etc._, and these capabilities cooperate with facilities defined in `replete.io`.

Replet core also hosts some dynamic vars of interest like `*in*` and `*out*`.

The `replete.core/file-seq` function imitates `clojure.core/file-seq`.

The `replete.core` namespace defines dynamic functions like `resolve`, `ns-resolve`, and `intern`.

### replete.io

([Online docs](replete-io.html))

This namespace defines a lot of the `IOFactory` machinery, imitating `clojure.java.io`.

Additionally, filesystem facilities like `file`, `delete-file`, and `file-attributes` are available.

### replete.http

([Online docs](replete-http.html))

This namespace provides facilities for interacting with HTTP servers. For example:

```
(replete.http/get "http://replete-repl.org")
```

will fetch the main page of the Replete website, returning the status code, headers, and body in a map structure.
