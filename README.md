# WindowProxy Spec Sketch

This is a first attempt at a more rigorous spec for [WindowProxy](https://html.spec.whatwg.org/multipage/browsers.html#the-windowproxy-object). This was prompted by [W3C Bugzilla Bug 27502](https://www.w3.org/Bugs/Public/show_bug.cgi?id=27502).

This shouldn't be taken as "official," or implemented: it's just a place to store the work before it moves to a real spec like WebIDL or HTML.

## WindowProxy Exotic Objects

A _window proxy_ is an exotic object that wraps a `Window` object, indirecting most operations through to the wrapped object. Each browsing context has a window proxy. When the browsing context is navigated, the `Window` object wrapped by the browsing context's window proxy is changed.

Every window proxy object has a [[Window]] internal slot representing the wrapped window.

The internal methods of window proxies are defined as follows, for a window proxy _O_. In all cases, let _W_ be the value of the [[Window]] internal slot of _O_.

### [[IsExtensible]\] ()

1. Return **true**.

### [[PreventExtensions]\] ()

1. Return **false**.

### [[GetOwnProperty]\] (P)

1. Let _desc_ the result of calling the [[GetOwnProperty]] internal method of _W_ with argument _P_.
2. Set _desc_.[[Configurable]] to **true**.
3. Return _desc_.

### [[DefineOwnProperty]\] (P, Desc)

1. If _desc_.[[Configurable]] is **false**, then throw a **TypeError** exception.
1. Return the result of calling the [[DefineOwnProperty]] internal method of _W_ with arguments _P_ and _Desc_.

### All other internal methods

All other internal methods must return the result of calling the corresponding internal method of _W_, passing along all arguments.
