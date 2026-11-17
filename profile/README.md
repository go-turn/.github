<p align="center"><img src="https://raw.githubusercontent.com/go-turn/brand/main/social/go-turn.png" alt="go-turn" width="720"></p>

# go-turn

**STUN and TURN in pure Go — a relay for WebRTC peers that cannot reach each other directly.**

A symmetric NAT, a full-tunnel VPN, or a network that only lets HTTPS out: in each
of those two peers cannot open a connection to one another, and something on the
public Internet has to carry the traffic. This organisation is that something, in
`CGO_ENABLED=0` Go, as one daemon on one host:

- **STUN and TURN** (RFC 8489, RFC 8656), reached over UDP, TCP, or TLS on 443;
- **short-lived credentials**, minted only after an OpenID Connect login through
  [go-authn](https://github.com/go-authn);
- **a rendezvous**, so a host opens a room, shares one link, and the guest's answer
  comes back on its own, over gRPC carried on a WebSocket.

It is the relay the [go-tex playground](https://go-tex.github.io/playground/) uses
for live collaboration over [go-crdt/collab](https://github.com/go-crdt/collab).

## Repositories

| Repo | Role |
| --- | --- |
| [`turn`](https://github.com/go-turn/turn) | The relay and its daemon `turnd`: the STUN/TURN codec and server, the credential scheme, the OIDC login, the gRPC rendezvous, and `turnprobe` to prove a deployment end to end. |
| [`brand`](https://github.com/go-turn/brand) | Logo, favicon and social banner. |
| [`docs`](https://github.com/go-turn/docs) | Documentation, published at [go-turn.github.io/docs](https://go-turn.github.io/docs/). |

📖 **[go-turn.github.io](https://go-turn.github.io/)** · **[Documentation](https://go-turn.github.io/docs/)**
