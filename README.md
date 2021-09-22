## Introduction
[bcc-container](https://hub.docker.com/r/pranavbhatt/bcc/) is provided for user to try out [bcc](https://github.com/iovisor/bcc) in a containerized environment. Where this fork differs is if you run an environment with old bcc tools, and you need some of the "relatively" new features.

To get started, run the following:
```bash
docker run -it --rm \
  --privileged \
  -v /lib/modules:/lib/modules:ro \
  -v /usr/src:/usr/src:ro \
  -v /etc/localtime:/etc/localtime:ro \
  pranavbhatt/bcc:0.1 <bpfcc tool>
```

## With minikube

To get this working with minikube, just follow [this tutorial](https://minikube.sigs.k8s.io/docs/tutorials/ebpf_tools_in_minikube/) until the last step, where you should instead run:
```bash
minikube ssh -- docker run --rm
  --privileged
  -v /lib/modules:/lib/modules:ro
  -v /usr/src:/usr/src:ro
  -v /etc/localtime:/etc/localtime:ro
  pranavbhatt/bcc:0.1 execsnoop-bpfcc
```

> Note: If you want to run it with a newer minikube image, the easiest (and slightly cheeky) way to do it would be to just rename the linux headers folder to whatever minor version your image requires. 
>
> Yes this won't guarantee bpfcc-tool operating correctly, but since at the time of writing there have only been changes to the minor version of the headers, they should ideally work just fine.
> 
> In the near future I might consider maintaining up-to-date headers for minikube if there is enough demand to do so.


## About
This repository is forked from [zlim/bcc](https://github.com/zlim/bcc-docker), but instead makes use of the `bpfcc-tools` package maintained by [@hadret](https://launchpad.net/~hadret) over [here](https://launchpad.net/~hadret/+archive/ubuntu/bpfcc). The list of tools are available [here](https://reposcope.com/package/bpfcc-tools).

For examples, please refer to the [bcc tutorial](https://github.com/iovisor/bcc/tree/master/docs/tutorial.md#1-general-performance).
