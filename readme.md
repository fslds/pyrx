pyrx with error messages
====

Python implementation of the [Rx schema and validation system](http://rx.codesimply.com/)

Fork of [pyrx](https://github.com/uniphil/pyrx) with added error messages. Most of the readme is also taken from there, just with updated usage instuctions.


Forked
------

Forked from the main [rx github repo](https://github.com/rjbs/rx) Nov 25 '13
because the python implementation deserves its own place and testing and stuff.

The copyright line of the license for the rx repository reads:

    The contents of the Rx repository are copyright (C) 2008, Ricardo SIGNES.

The license itself is GPL2: https://github.com/rjbs/rx/blob/master/LICENSE


Requirements
------------

* No external dependencies
* Python2.7


Usage
-----

```python
import pyrx

rx = pyrx.Factory({"register_core_types": True})

schema_src = {
  "type": "//rec",
  "required": {
    "a": "//str",
    "b": "//int",
  },
  "optional": {
    "c": "//bool",
  },
}

schema = rx.make_schema(schema_src)

schema.check({"a": "a string", "b": 2}).valid  # returns True
schema.check({"a": "a string", "b": "another string"}).valid  # returns False
schema.check({"a": "a string", "b": "another string"}).message  # returns an error message

```


Testing
-------

py.test test/

