jquery-objectdiff  - a jQuery plugin
====================================

This plugin is just a helper function for calculating a diff of two similar
objects ala ActiveRecord's [changes](http://api.rubyonrails.org/classes/ActiveModel/Dirty.html#method-i-changes) 
hash. Just pass in two objects and this function will return an object of
changes that contains only the properties that have changed.

Differences are stored in arrays; the first element has the 'before' valueand
the second element is the 'after' value.

Usage:
------

```javascript
    var before = {id:123, name:{first:"Johnny", last:"Johnson"}};
    var after = {id:123, name:{first:"John", last:"Johnson"}, age:30};
    var changes = $.objectDiff(before, after);
```

Result (contents of changes):
-----------------------------

```javascript
    {name: {first:["Johnny","John"]}, age:[undefined,30]}
```

