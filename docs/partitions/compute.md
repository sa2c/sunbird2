# SUNBIRD2 CPU partitions

SUNBIRD2 has two CPU-based partitions for general use:

- `compute`: standard-memory (768 GiB per node)
- `highmem`: high-memory (1.5TiB per node)

Each of these nodes has two AMD EPYC 9555 64-core CPUs,
each of which is configured to have four NUMA domains.
As such,
it's advisable to use a minimum of eight MPI process per node,
each allocating 16 threads.

Jobs can take up to 72 hours on these partitions.
