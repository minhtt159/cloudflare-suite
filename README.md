# Utilize Cloudflare services on Kubernetes and Docker

## Motivation / Goal

We're going to integrate the Cloudflare suite to expose our services to the internet.

1. Cloudflare DNS

User (ask for domain) -> Internet -> Cloudflare -> Else-where

2. Cloudflare Tunnel

Cloudflare -> Cloudflare tunnel agent -> Local services

## Pre-requisite

1. You must have your domain and point the nameserver to Cloudflare first.
2. Create a tunnel 
3. Add to config

## Explain (Kubernetes)

1. [External-DNS](https://github.com/kubernetes-sigs/external-dns) 

ExternalDNS makes Kubernetes resources discoverable via public DNS servers. This service will create DNS records to point to the Cloudflare tunnel agent.

2. [Cloudflare tunnel](https://github.com/cloudflare/cloudflared)

Cloudflare tunnel route traffics between the Cloudflare network and your origin. 

3. (Optional) [Error-pages](https://github.com/tarampampam/error-pages)

Provide pretty server error pages.

### Deploy

https://github.com/cloudflare/argo-tunnel-examples/blob/master/named-tunnel-k8s/cloudflared.yaml