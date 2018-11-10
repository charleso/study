# Big Metadata

Being able to track files in S3 (or HDFS) in an atomic way is crucial for
reasoning about the state of data in your system.


## Iceberg

Still very young, and it's really just a data format plus some client libraries.
Missing lots of tooling, like a CLI, at this stage.

- https://github.com/Netflix/iceberg

Netflix clearly consume the results from their own metadata service:

- https://github.com/Netflix/metacat

Could be used in conjunction with a separate lineage tracking system:

- https://github.com/MarquezProject/marquez


## Hudi

Much more polished than Iceberg, but also looks much more complicated.
Has a CLI and UI which is nice.

- https://github.com/uber/hudi
- https://eng.uber.com/hoodie/
