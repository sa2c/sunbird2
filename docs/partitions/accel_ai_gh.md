# AccelerateAI Grace Hopper nodes

In addition to the primary A100-based partition,
AccelerateAI has two nodes containing Grace Hopper Superchips.

## Compiling for Grace Hopper

Grace Hopper uses a different CPU architecture (arm64)
to that used in the rest of SUNBIRD2 (x86-64).
As such,
the modules installed on most of SUNBIRD2 won't work on AccelerateAI-GH,
and vice-versa;
neither will
any software you compile on the SUNBIRD2 login node
work on the AccelerateAI-GH compute nodes.

Instead,
we recommend you start an interactive session on one of the AccelerateAI-GH nodes
in order to explore what modules are available,
and install and build your software.
To start an interactive allocation,
run:

```
srun --account scw0123 --partition accel_ai_gh --nodes 1 --ntasks 1 --cpus-per-task 4 --pty --time 4:00:00 /bin/bash
```

You will now see the prompt change to indicate that you are running on
`sb-gh001` or `sb-gh002`.
`module available` will show only modules that work on Grace Hopper,
with which you can now compile your software.

Once you are finished compiling,
you can exit the interactive session by running `exit`,
and prepare and submit a job script as you would for other partitions.
