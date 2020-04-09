# numbers
Some interesting numbers in systems programming, with references.

| Type | Size | Switch latency (order of magnitude) / cost | Notes | 
| --- | --- | --- | --- | 
| Erlang process | [309 machine words](http://erlang.org/doc/efficiency_guide/processes.html) (8 Bytes * 309 on 64bit arch) | | Stack size is dynamic, garbage collection runs per user space thread |
| Golang process | [2kB](https://github.com/golang/go/blob/98b6c6aca6fd4185f97dc40137707f4d8df8aa7c/src/runtime/stack.go#L72) | [~170 ns](https://eli.thegreenplace.net/2018/measuring-context-switching-and-memory-overheads-for-linux-threads/) | dynamically allocated
| Linux thread | `ulimit -s` gives me 8MiB on my machine; | [~2us](https://eli.thegreenplace.net/2018/measuring-context-switching-and-memory-overheads-for-linux-threads/) for a context switch | 
| Linux process creation | | [~5us](https://eli.thegreenplace.net/2018/launching-linux-threads-and-processes-with-clone/)
| Linux thread creation | | [~35us](https://eli.thegreenplace.net/2018/launching-linux-threads-and-processes-with-clone/)|  
| Linux rseq | 
