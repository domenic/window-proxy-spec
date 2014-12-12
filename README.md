# WindowProxy Spec Sketch

This is a first attempt at a more rigorous spec for [WindowProxy](https://html.spec.whatwg.org/multipage/browsers.html#the-windowproxy-object). This was prompted by [W3C Bugzilla Bug 27502](https://www.w3.org/Bugs/Public/show_bug.cgi?id=27502).

This shouldn't be taken as "official," or implemented: it's just a place to store the work before it moves to a real spec like WebIDL or HTML.

## WindowProxy Exotic Objects

A _window proxy_ is an exotic object that wraps a `Window` object, indirecting most operations through to the wrapped object. Each browsing context has a window proxy. When the browsing context is navigated, the `Window` object wrapped by the browsing context's window proxy is changed.

Every window proxy object has a [[Window]] internal slot representing the wrapped window.

The internal methods of window proxies are defined as follows, for a window proxy _O_. In all cases, let _W_ be the value of the [[Window]] internal slot of _O_.

### [[GetPrototypeOf]\] ()

1. Return the result of calling the [[GetPrototypeOf]] internal method of _W_.

### [[SetPrototypeOf]\] (V)

1. Return the result of calling the [[SetPrototypeOf]] internal method of _W_ with argument _V_.

### [[IsExtensible]\] ()

1. Return the result of calling the [[IsExtensible]] internal method of _W_.

### [[PreventExtensions]\] ()

1. Return the result of calling the [[PreventExtensions]] internal method of _W_.

### [[GetOwnProperty]\] (P)

1. Return the result of calling the [[GetOwnProperty]] internal method of _W_ with argument _P_.

### [[DefineOwnProperty]\] (P, Desc)

1. Return the result of calling the [[DefineOwnProperty]] internal method of _W_ with arguments _P_ and _Desc_.

### [[HasProperty]\] (P)

1. Return the result of calling the [[HasProperty]] internal method of _W_ with argument _P_.

### [[Get]\] (P, Receiver)

1. Return the result of calling the [[Get]] internal method of _W_ with arguments _P_ and _Receiver_.

### [[Set]\] (P, V, Receiver)

1. Return the result of calling the [[Set]] internal method of _W_ with arguments _P_, _V_, and _Receiver_.

### [[Delete]\] (P)

1. Return the result of calling the [[Delete]] internal method of _W_ with argument _P_.

### [[Enumerate]\] ()

1. Return the result of calling the [[Enumerate]] internal method of _W_.

### [[OwnPropertyKeys]\] ()

1. Return the result of calling the [[OwnPropertyKeys]] internal method of _W_.

### [[Call]\] (thisArgument, argumentsList)

1. Return the result of calling the [[Call]] internal method of _W_ with arguments _thisArgument_ and _argumentsList_.

### [[Construct]\] (argumentsList)

1. Return the result of calling the [[Construct]] internal method of _W_ with argument _argumentsList_.
