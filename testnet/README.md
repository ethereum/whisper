# Testnet node

This `Dockerfile` can be used to create a testnet client.

## Installation

On a Linux machine, in the same directory as the `Dockerfile`, type:

```shell
$ docker build -t whisper_testnet .
```

## Running

Type:

```shell
docker run -it whisper_testnet
```

## Private network

It is also possible to tweak this file in order to create your own private network (no metadata safety garantee, obviously).
