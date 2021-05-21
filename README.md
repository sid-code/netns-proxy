# netns-proxy

A simple and slim proxy to forward ports from and into linux network
namespaces.


## Overview

`netns-proxy` is a plain and simple proxy for TCP, UDP and SCTP that allows to
accept connections in one network namespace and forwards them into another.

This allows to expose ports that are only accessible in one namespace to a
second one. This provides a lightweight alternative to connecting namespace with
`veth` interfaces which require address management and firewall rules for
forwarding.

`netns-proxy` does its job by opening a socket when it is started and switches
to the target namespace before opening connections to the exposed server. This
allows the accepting socket to exist in the original namespace while forwarded
connection happen in the specified namespace.


## Usage

```
netns-proxy <netns> <target>
```

`<netns>` is the name of the network namespace from which forwarded connections
are created.

`<target>` the target host and port to forward connections to.

See `netns-proxy --help` for full details and options.


## Getting Help

Feel free to open an [Issue](https://github.com/fooker/netns-proxy/issues) or
write me a [Mail](mailto:fooker@lab.sh).


## Contributing

:+1: Thanks for your help to improve the project! Pleas don't hesitate to
create an [Issue](https://github.com/fooker/netns-proxy/issues) if you find
something is off or even consider creating a patch and propose a Pull-Request.


## License

The project is licensed under the [MIT license](./LICENSE).
