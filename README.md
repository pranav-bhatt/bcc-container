## Introduction
[bcc-docker](https://hub.docker.com/r/pranavbhatt/bcc/) is provided for user to try out [bcc](https://github.com/iovisor/bcc).

To get started, run the following:
```bash
docker run -it --rm \
  --privileged \
  -v /lib/modules:/lib/modules:ro \
  -v /usr/src:/usr/src:ro \
  -v /etc/localtime:/etc/localtime:ro \
  --workdir /usr/share/bcc/tools \
  pranavbhatt/bcc:0.1 <bpfcc tool>
```

## About
This repository is forked from [zlim/bcc](https://github.com/zlim/bcc-docker), but instead makes use of the `bpfcc-tools` package maintained by [@hadret](https://launchpad.net/~hadret) over [here](https://launchpad.net/~hadret/+archive/ubuntu/bpfcc). The list of tools are available [here](https://reposcope.com/package/bpfcc-tools).

For examples, please refer to the [bcc tutorial](https://github.com/iovisor/bcc/tree/master/docs/tutorial.md#1-general-performance).
