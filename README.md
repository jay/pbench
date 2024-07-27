# MODIFIED

**This is a version of pbench that I modified to remove minimum field width
from the IO output format and to build with an old version of Visual Studio.**

For testing curl issue https://github.com/curl/curl/pull/14274

# pbench

The pbench is Windows equivalent to Unix "time" command to measure
process resource usage.

## Syntax

```
pbench [OPTIONS] COMMAND [ARGS]
```

## Parameters
| Parameter        | Description                                           |
|------------------|-------------------------------------------------------|
| --pid PID        | Also benchmark process with specified process ID      |
| --count COUNT    | Run command COUNT times                               |
| --concurrent     | Run command in parallel                               |
| --stdout-nul     | Redirect command output to NUL                        |

## Examples

Measure performance of `curl -v -4 localhost:6789` command:

```Batchfile
pbench --count 5 curl -v -4 localhost:6789
```

```Console
== Performance of curl -v -4 localhost:6789

The command was run 5 times.

                 average     minimum     maximum
   Real time:    1.042 s     1.035 s     1.046 s
    CPU time:    0.012 s     0.000 s     0.015 s
   User time:    0.006 s     0.000 s     0.015 s
 Kernel time:    0.006 s     0.000 s     0.015 s
     Read IO:        1 (0 KB)  1 (0 KB)  1 (0 KB)
    Write IO:        0 (0 KB)  0 (0 KB)  0 (0 KB)
    Other IO:      134 (2 KB)  132 (2 KB)  135 (2 KB)
Peak WS size:     6059 KB  6040 KB  6076 KB

  Total time:    5.215 s
```
