Two flavors of sets:

* In-memory and persistable to disk.
* On-disk (persisted).

Performance characteristics:

* Size in memory.
* Size on disk.
* Insertion speed when the set is large.
* Time to serialize to/deserialize from disk when large.

Requirements on items:

* Implements Hash + Eq (hash based sets).
* Implements Ord (tree based sets).
* Representable as &[u8] (BerkeleyDB, sled).

Aspects of testing:

* Making sure the API supports all backends:
    * Testing the API with fake implementors that require different traits on items.
* Making sure the API exposes the right set of operations wrt. to all backend lifecycles:
    * Testing the API with fake implementors that are either persistable or persisted.
* Measuring performance and resource usage (ie. benchmarks):
    * Testing against all real backends.
* Assuring correctness during parallel access.
    * Testing insertion/membership check with multiple threads.

Desired crate characteristics:

* Each backend is a dependency that can be enabled separately.