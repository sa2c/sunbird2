# Running jobs on SUNBIRD2

Since SUNBIRD2's resources are shared between many people,
to ensure that different jobs cannot interfere with each other,
and start in an appropriate order,
SUNBIRD2 makes use of the [Slurm workload scheduler][slurm].

!!! important
    ## Do not run on the login node

    If you're familiar with Unix-based systems,
    your first instinct might be to start running work interactively
    on the first node you connect to.
    This will not give good performance,
    and will interrupt others' work;
    the login nodes are for setting up your environment and submitting jobs from.
    Slurm passes these jobs to the compute nodes to actually do the work.

## Submitting a job

To instruct Slurm on what work you want performed as part of a job,
you write a [shell script][shell].
You can add specially-formed comments to this to instruct Slurm on what resources your job needs.
An example job script:

```
#!/bin/bash
#SBATCH --job-name testjob
#SBATCH --output test.%j.out
#SBATCH --partition compute
#SBATCH --account scw0123
#SBATCH --nodes 1
#SBATCH --ntasks-per-node 8
#SBATCH --cpus-per-task 16
#SBATCH --time 12:00:00

module purge
module load gnu/15.3.0 mpi/openmpi/5.0.10-gnu-15.3.0

srun ./myapp input.xml
```

Key points here:

- Directives to Slurm are prefixed with `#SBATCH`,
  and must sit at the top of the file
  (before any shell commands to be executed)
- Use `--account` to specify your Supercomputing Wales project identifier,
  so we know what the work is in service of.
  If you don't yet have a Supercomputing Wales project,
  see [Getting access](access.md)
- Specify the number of nodes, tasks, and CPUs your code is able to use.
- Set a time limit on your jobs that is not much larger than the real time requirement.
  The shorter the time limit,
  the faster the job will start.
  Slurm has to play higher-dimensional Tetris with our jobs to maximise the utilisation of the machine;
  smaller pieces fit better.
  
!!! note
    ## Time limits

    You can check the maximum time limit for the partition you are targeting
    by using the `sinfo` command.
    
    If you need to run longer than this,
    in exceptional cases you can fill out the [non-standard job request][nonstandard].
    However,
    if this will be a recurring requirement,
    we will ask you to investigate implementing checkpointing in your software,
    so that it can save its state and resume in a future iteration.
    This is so that Slurm is able to let other users' jobs get a chance to start,
    and avoid fragmenting and clogging the queue.

For more information on using Slurm and preparing and submitting job scripts,
see [HPC Carpentry][hpc-carpentry].

!!! note
    For information about running on specific partitions,
    please see the specific pages linked to the left.

## Checking job status

To see what jobs are in the queue,
run

```
squeue
```

This will give a listing of all users' jobs.
To see just your own jobs,
use

```
squeue --me
```

Here you will see a listing of all jobs that are running,
or waiting to run.

## Cancelling a job

If a job has stopped giving useful output but is still running,
or has not yet started but you not longer want it to,
you can cancel it.
Note the job ID
(the leftmost column in `squeue`),
and run

```
scancel [jobid]
```

This makes sure that you aren't wasting resources that others could be using in their work.


[hpc-carpentry]: <https://carpentries-incubator.github.io/hpc-intro/>
[nonstandard]: <https://forms.cloud.microsoft/e/q5EnhczjqC>
[shell]: <https://swcarpenrty.github.io/shell-novice>
[slurm]: <https://slurm.schedmd.com/overview.html>
