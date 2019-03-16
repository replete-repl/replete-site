## REPL

<img width="130" align="right" style="margin: 0ex 1em" src="img/repl.jpg">
When launched, Replete will enter an interactive Read-Eval-Print Loop, or _REPL_.

Replete starts off with `cljs.user` as the _current namespace_. 

> In ClojureScript, `def` and derived forms create vars in the current namespace. In addition, unqualified non-local symbols are resolved to vars in the current namespace.

You can enter forms to be evaluated in the text box. When you tap the "Eval" button, the form, and any printed output, and the value of the evaluated form will be displayed above the text box.


Try evaluating `(+ 1 2)` and `3` will be displayed. Or, try `(println "Hi")` and `Hi` will be displayed followed by `nil` (the value of the `println` call).

You can hit return prior to typing a complete form and the text box will increase in height to accommodate additional input. Multi-line input can continue this way until a full form is entered.

```clojure-repl
(defn square
  [x]
  (* x x))
```

When entering forms, closing delimiters will be automatically entered and managed using [Parinfer](https://shaunlebron.github.io/parinfer/). 

#### History

You can copy any previously entered form, output, or result by long pressing on the row containing the item to be copied.

### Result Display

When you evaluate a form, the result is pretty printed using [Fipp](https://github.com/brandonbloom/fipp). This causes output to be wrapped and aligned in a manner that makes it easier to see the structure of the data.

### REPL Specials

REPL specials are, in essence, special forms that exist only in the REPL. (They can't be used in regular ClojureScript code and must be entered as top-level forms.)

#### in-ns 

Replete supports `in-ns`, which will switch you to a new namespace, creating it if it doesn't already exist.

```clojure-repl
(in-ns 'bar.core)
nil
```

As in Clojure, Replete's `in-ns` REPL special accepts any expression, so long as it evaluates to a symbol, so you can do something like this

```clojure-repl
(def my-ns 'foo.core)
#'cljs.user/my-ns
(in-ns my-ns)
nil
```

#### doc, source, pst, apropos, find-doc, dir

Usually in CloureScript, `doc` is a macro that you refer. In Replete these are REPL specials which are always available, no matter which namespace you are in.
