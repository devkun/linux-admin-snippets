# Misc.

* SHA1 hash in base64
```bash
ruby -r digest/sha1 -e 'puts Digest::SHA1.base64digest("abc123")'
```

* K8s port forwarding
```bash
sudo -E kubectl port-forward -n traefik svc/traefik --address=127.0.0.100 80:80 443:443
sudo -E kubectl port-forward -n ingress-nginx svc/ingress-nginx-controller --address=127.0.0.101 80 443
```

* Change MTU for routes
```bash
ip r ls table 220 | while read line
do
  ip r change table 220 $line mtu 1340
done
```
