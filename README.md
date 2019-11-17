A set that supports insertion and membership checking with multiple
implementations (backends). Other set operations are not supported.

Each backend is either persistent (on-disk) or persistable (in-memory but
supports serializing/deserializing).

Major goals:

* Optimize memory usage (if in memory).

Secondary goals:

* Optimize disk usage (if on disk).
* Runtime speed of insertion / membership check.
