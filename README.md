A trivial bash wrapper script
-----------------------------

Running `perf stat cmd args` returns 0 even when `cmd` is killed by a signal
(say, SIGSEGV for a segfault, or SIGKILL).

Reference: https://stackoverflow.com/a/34803514.

After installing this package, you can run `perf stat bash-wrap cmd args`
instead, which will fail if `cmd` is killed (with the same error code as
`cmd` — `128 + signal_number`, so 139 for `SIGSEGV`).
