# WindowProxy Spec Sketch

This is a first attempt at a more rigorous spec for [WindowProxy](https://html.spec.whatwg.org/multipage/browsers.html#the-windowproxy-object). This was prompted by [W3C Bugzilla Bug 27502](https://www.w3.org/Bugs/Public/show_bug.cgi?id=27502).

This shouldn't be taken as "official," or implemented: it's just a place to store the work before it moves to a real spec like WebIDL or HTML.

## WindowProxy Exotic Objects

A _window proxy_ is an exotic object that wraps a `Window` object, indirecting most operations through to the wrapped object. Each browsing context has a window proxy. When the browsing context is navigated, the `Window` object wrapped by the browsing context's window proxy is changed.

Every window proxy object has a [[Window]] internal slot representing the wrapped window.

The internal methods of window proxies are defined as follows:

### [[GetPrototypeOf]\] ()

### [[SetPrototypeOf]\] (V)

### [[IsExtensible]\] ()

### [[PreventExtensions]\] ()

### [[GetOwnProperty]\] (P)

### [[DefineOwnProperty]\] (P, Desc)

### [[HasProperty]\] (P)

### [[Get]\] (P, Receiver)

### [[Set]\] (P, V, Receiver)

### [[Delete]\] (P)

### [[Enumerate]\] ()

### [[OwnPropertyKeys]\] ()

### [[Call]\] (thisArgument, argumentsList)

### [[Construct]\] (argumentsList)
