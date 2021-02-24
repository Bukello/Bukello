## Progress in 2019-2020

* New functionality
  * added transaction durability option, per discussion at TPAC 2019 #50
    * Supported in Chrome and Edge
* Other normative changes
  * remove File lastModifiedDate references, per discussion at TPAC 2019 #215
  * specify that read-only transactions can run in parallel but block a later read/write transaction from starting, and the read/write transactions similarly block later read/write and read-only transactions, matching implementations #253 
  * disallow proxies as keys, matching implementations. #309
  * make transactions inactive during the value clone process, to prevent side effects (e.g. getters) from re-entering algorithms. 
* Spec quality 
  * Alignment with [Infra](https://infra.spec.whatwg.org/) and [WebIDL](https://heycam.github.io/webidl/) syntax, term and convention updates.
  * Added Accessibility Concerns section #327

Pending changes:
* New functionality
  * (has [PR](https://github.com/w3c/IndexedDB/pull/343)) IDBObjectStore putAll() per TPAC 2019 discussion - Chrome has implementation experience, but no data ready to share yet.
  * (has [PR](https://github.com/w3c/IndexedDB/pull/331)) Manual commit per TPAC 2019 discussion - no implementation plans I'm aware of.
  * (has [PR](https://github.com/w3c/IndexedDB/pull/280)) IDBObjectStore / IDBIndex getAllEntries() per TPAC 2019 discussion  - 
no implementation plans I'm aware of.
  * (has [PR](https://github.com/w3c/IndexedDB/pull/302)) IDBCursor close() per TPAC 2019 discussion - no implementation plans I'm aware of.
* Spec quality
  * (has [PR](https://github.com/w3c/IndexedDB/pull/334)) Define Indexed DB as a storage endpoint, per Storage, and integrate with "bottles" terms, etc.

## Moving to CR

Seems premature:

* Goals for V3 in charter state _"The third edition adds new capabilities and improves developer ergonomics by using promises."_ [KV-Storage](https://wicg.github.io/kv-storage/) as a Promise-based layer on top of Indexed DB has stalled. An alternative is to push on low-level support in Indexed DB ([example](https://github.com/w3c/IndexedDB/pull/331)) and encourage libraries to implement Promise support.
* Overall, new functionality since V2 is limited: see https://w3c.github.io/IndexedDB/#revision-history
   * `databases()` method #31, `commit()` method #234, `request` attribute #255, `durability` option #50

How to unblock:

* IMHO, at least one more "big" feature is needed (e.g. one of the above PRs) to justify the effort
* Need further implementation experience
* Any other interested editors? Both current editors are from Chromium-based browsers.
* Need a WD published at least.

## See also

* [TPAC 2019 report](https://github.com/w3c/IndexedDB/issues/290)
