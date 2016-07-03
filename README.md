Let's say you want to compare two programs to see which maximizes some figure of merit.
Let's say you're doing this on a machine that's not 100% idle or 100% isolated.
You could run one of them under some kind of statistical harness, like `perf stat --repeat=50`, then the other, and compare the results.
Is that good enough?
No, because system parameters drift.
In particular, your benchmark machine is substantially warmer for the second set of runs, which may affect e.g. DVFS parameters.

These are some simple scripts to address that using the principles of randomized controlled trials.
Your test programs are run interleaved in a random order to decorrelate parametric drift from which test program is being run.
Afterward, error estimates are generated.
No detrending or other corrections are done.
Caveat emptor.

This program is placed into the public domain.
