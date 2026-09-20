# Module 2 — Computer Networking Basics: Answers


## Exercise 1 — Client and Server

The first command started the server.

When I used `curl localhost:8080`, I was the **client** because curl sent a request to the server.

---

## Exercise 2 — Subnet Mask Bit Calculation

| CIDR | Host bits | Usable hosts |
|---|---:|---:|
| /24 | 8 | 254 |
| /16 | 16 | 65,534 |
| /28 | 4 | 14 |
| /26 | 6 | 62 |

Formula:

`Usable hosts = 2^(host bits) - 2`

---

## Exercise 3 — Default Gateway

Default gateway:

`10.0.0.1`

Codespace IP:

`10.0.12.219/16`

Yes, the default gateway and the Codespace IP are on the same subnet.

---

## Exercise 4 — Two Servers on One Machine

Two ports were listening:

- Port 8080
- Port 8081

Both servers were running on the same machine but used different ports.

`curl localhost:8080` and `curl localhost:8081` created two separate conversations.

---

## Exercise 5 — URL Components

URL:

`http://localhost:8080/predict.txt`

- Protocol: `http`
- Host: `localhost`
- Port: `8080`
- Path: `/predict.txt`

Requesting:

`curl localhost:8080/predict.txt`

returned:

`hello`

Requesting:

`curl localhost:8080/missing.txt`

returned:

`404 File Not Found`

---

## Exercise 6 — DNS

The DNS TTL was:

`300 seconds`

This equals:

`5 minutes`

The IP addresses returned by `dig example.com` were:

- `172.66.147.243`
- `104.20.23.154`

`ping` used:

`104.20.23.154`

This matched one of the IP addresses returned by `dig`.

However, ping did not receive replies:

`4 packets transmitted, 0 received, 100% packet loss`

---

## Exercise 7 — Network Configuration

My Codespace IP address was:

`10.0.12.219/16`

`ip a` shows the IP address of my Codespace machine.

The gateway IP is shown separately using `ip route`.

---

## Exercise 8 — Network Toolkit

`curl -I https://example.com` returned only the HTTP response headers, such as:

- HTTP status
- Content-Type
- Server
- Last-Modified

A normal `curl` request returns the page body/content, while `curl -I` returns headers only.

The `ss -tulnp` command displayed the TCP/UDP ports currently listening on the Codespace.