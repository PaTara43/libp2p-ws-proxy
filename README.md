# Libp2p <-> Websocket Proxy

Module for message proxying between libp2p channels and WebSocket clients, and vice versa. Currently Libp2p nodes supports web socket transport via relay chain.

## Running

### Docker

---

Requirements:
1. Docker

Build:

Pull the iamge:
```
docker pull ghcr.io/pinoutltd/libp2p-ws-proxy:latest
```

Launch:

To enable access to the WebSocket server from another application, it is essential to establish a port mapping between the host and the container. While not mandatory, it is advisable to align the port numbers in the container and on the host.
```
docker run --name libp2p-proxy --detach -p 127.0.0.1:8888:8888 -p 127.0.0.1:9999:9999 proxy:v0.0.1
```

To see logs:
```
docker run --name libp2p-proxy --detach -p 127.0.0.1:8888:8888 -p 127.0.0.1:9999:9999 ghcr.io/pinoutltd/libp2p-ws-proxy:latest
```

To stop the container:

```
docker stop libp2p-proxy
```

### From Source
---

Requirements:
1. Node v.20.10.0

Installation:

```
git clone https://github.com/PinoutLTD/libp2p-ws-proxy.git
cd libp2p-ws-proxy
npm install
```

Launch:

```
node src/index.js
```
Then you can connect a websocket client and libp2p nodes to proxy messages between them.