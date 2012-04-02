# node-touch

For all your node touching needs.

__WARNING__: This library depends on `fs.futimes` which has been
introduced to the `fs` module with the release of __0.6__. To achieve
some kind of compatibility with prior versions, setting __atime__ and
__mtime__ is simply omitted. If you need this feature, update your node
version!

## CLI Usage:

See `man touch`

## API Usage:

```javascript
var touch = require("touch")
```

Gives you the following functions:

* `touch(filename, options, cb)`
* `touch.sync(filename, options)`
* `touch.ftouch(fd, options, cb)`
* `touch.ftouchSync(fd, options)`

## Options

* `force` like `touch -f` Boolean
* `time` like `touch -t <date>` Can be a Date object, or any parseable
  Date string, or epoch ms number.
* `atime` like `touch -a` Can be either a Boolean, or a Date.
* `mtime` like `touch -m` Can be either a Boolean, or a Date.
* `ref` like `touch -r <file>` Must be path to a file.
* `nocreate` like `touch -c` Boolean

If neither `atime` nor `mtime` are set, then both values are set.  If
one of them is set, then the other is not.
