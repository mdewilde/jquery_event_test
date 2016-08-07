# jQuery Event Test

Performance test of four different patterns for attaching events with jQuery. 

### Setup

The test starts by creating a reasonably sized DOM hierarchy with 10 DIV hierarchies, each 15 levels deep, containing 4 links inside each DIV.

A delegated event, attached to `document`, is added to each link.

One link is chosen at random from the entire collection of available links and clicked 15 times programmatically.


### Pattern 1

```JavaScript
a.on('click', function() {
	// action
});
```

### Pattern 2

```JavaScript
a.on('click', function(e) {
	e.stopPropagation();
	// action
});
```

### Pattern 3

```JavaScript
$(document).on('click', '.clazz', function() {
	// action
});
```

### Pattern 4

```JavaScript
$(document).on('click', '.clazz', function(e) {
	e.stopPropagation();
	// action
});
```
### Results

```
Pattern 1 --> 3644 ms
Pattern 2 -->    2 ms
Pattern 3 --> 3589 ms
Pattern 4 --> 3496 ms
```

_(Firefox 47, Fedora 23, Intel i5-2500k, 16GB RAM)_
