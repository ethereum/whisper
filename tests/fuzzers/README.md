## Fuzzers

To run a fuzzer locally, you need [go-fuzz](https://github.com/dvyukov/go-fuzz) installed. 

First build a fuzzing-binary out of the selected package:

```
(cd ./whisperv6 && CGO_ENABLED=0 go-fuzz-build .)
```

That command should generate a `rlp-fuzz.zip` in the `rlp/` directory. If you are already in that directory, you can do

```
[user@work rlp]$ go-fuzz
2020/07/24 19:10:39 workers: 6, corpus: 1 (3s ago), crashers: 0, restarts: 1/0, execs: 0 (0/sec), cover: 0, uptime: 3s
2020/07/24 19:10:42 workers: 6, corpus: 20 (0s ago), crashers: 0, restarts: 1/0, execs: 0 (0/sec), cover: 0, uptime: 6s
2020/07/24 19:10:45 workers: 6, corpus: 20 (3s ago), crashers: 0, restarts: 1/0, execs: 0 (0/sec), cover: 407, uptime: 9s
2020/07/24 19:10:48 workers: 6, corpus: 20 (6s ago), crashers: 0, restarts: 1/1095, execs: 13146 (1095/sec), cover: 407, uptime: 12s
2020/07/24 19:10:51 workers: 6, corpus: 20 (9s ago), crashers: 0, restarts: 1/3258, execs: 39100 (2606/sec), cover: 407, uptime: 15s
2020/07/24 19:10:54 workers: 6, corpus: 20 (12s ago), crashers: 0, restarts: 1/3943, execs: 63098 (3505/sec), cover: 407, uptime: 18s
2020/07/24 19:10:57 workers: 6, corpus: 20 (15s ago), crashers: 0, restarts: 1/5140, execs: 87388 (4161/sec), cover: 407, uptime: 21s
2020/07/24 19:11:00 workers: 6, corpus: 20 (18s ago), crashers: 0, restarts: 1/5299, execs: 111285 (4636/sec), cover: 407, uptime: 24s
2020/07/24 19:11:03 workers: 6, corpus: 20 (21s ago), crashers: 0, restarts: 1/6147, execs: 135240 (5008/sec), cover: 407, uptime: 27s
2020/07/24 19:11:06 workers: 6, corpus: 20 (24s ago), crashers: 0, restarts: 1/6336, execs: 158403 (5280/sec), cover: 407, uptime: 30s
...
```

