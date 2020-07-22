# whisper

This repository is extracted from [the go-ethereum whisper implementation](https://github.com/ethereum/go-ethereum) and is used as an archive.

The rationale for archiving this project is that it is obvious that in its current implementation, Whisper will never scale beyond a couple hundred nodes. Further development has now been taken on by [status](https://github.com/status-im/status-go/tree/develop/whisper).

It also contains various whisper-related tools.

## Building

Type `go build ./cmd/wnode` to build the Whisper node utility.
