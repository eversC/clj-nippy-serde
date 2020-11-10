# clj-nippy-serde

A nippy Serde for kafka

[![Clojars Project](https://img.shields.io/clojars/v/bigsy/clj-nippy-serde.svg)](https://clojars.org/bigsy/clj-nippy-serde)


## Usage

```clojure
(:require [clj-nippy-serde.serialization] :as :nser)

;; Create serde for kafka streams:
(def nippy-serde (nser/nippy-serde))

;; Create standard kafka serializers and deseializers
(def nippy-serializer (.serializer nippy-serde))
(def nippy-deserializer (.deserializer nippy-serde))

```

## Allow Listing Classes

From >= `clj-nippy-serde 0.1.3`, users will need to allowlist any classes
that are not natively supported by
[nippy](https://github.com/ptaoussanis/nippy/blob/e5a614bd9b6f7ec1d171ee0b35aabf9088173fe4/src/taoensso/nippy.clj#L283:L300)
by default.

This functionality was added to `nippy` to fix a
[CVE](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-24164).

Custom classes can be added via

1. an environment variable:

```bash
#!/bin/bash
export TAOENSSO_NIPPY_SERIALIZABLE_WHITELIST_ADD='java.time.OffsetDateTime'
# or
export TAOENSSO_NIPPY_SERIALIZABLE_WHITELIST_ADD='java.time.OffsetDateTime,other.class.1,other.class.2'
# etc.
```

2. a JVM property:

```
-Dtaoensso.nippy.serializable-whitelist-add=java.time.OffsetDateTime
or
-Dtaoensso.nippy.serializable-whitelist-add=java.time.OffsetDateTime,other.class.1,other.class.2
etc.
```


## License

Copyright © 2018 FIXME

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
