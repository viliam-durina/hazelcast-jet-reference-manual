This section covers the Core API, Jet's low-level API that directly
exposes the computation engine's raw features. If you are looking for
the API to build your computation pipeline, please refer to the
[Work With Jet](./Work_with_Jet) section.

Creating a Core API DAG requires expert-level familiarity with concepts
like partitioning schemes, vertex parallelism, distributed vs. local
edges, etc. Furthermore, this API offers no static type safety and it
is very easy to create a DAG that fails with a `ClassCastException` when
executed. Even though it is possible, this API is not intended to
create DAGs by hand; its purpose is to serve as the infrastructure on
top of which to build high-level DSLs and APIs that describe computation
jobs.

Implementing a Core API `Processor` requires even greater expertise than
building a DAG. Among other things, you have to be acquainted in detail
with Jet's concept of cooperative multithreading. While we provide as
much convenience as we can for extending Jet with your custom
processors, we cannot remove the dangers of using these facilities
improperly.