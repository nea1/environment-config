# environment-config


Clone flux repo, change deploy/flux-deployment.yaml to point to branch of this repo and deploy:

```
kubectl apply -f deploy
```

Get flux's public key:
```
kubectl logs deployment/flux | grep identity.pub | cut -d '"' -f2 | pbcopy
```

Add this as a deploy key in github with write access (Settings > Deploy Keys > Add new)

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDEFmPlcNHNDC9IP2gK9Bexn37ZioisEWez4Dy7Wl2hw52VPWs7kBnVbTgBf3atVtVIBdiXu7iWEKlcZ88VAg6WDIxOJB8dJ/dRfIPIiD55pivGWPcLeOlWjqoNkv+zphABdEpieRyXbzqdQnuRYfRBVfcR2XPrVw26k9UIv96gyrDZkGkfRJC2Jh0nIdaahbwJsu8j57VuHuMHQr5kGNl2cZspPnzBTfv9GHZZSp1LcFlCejAkjZuawi72PA27ZrpDXpnkIxWGWXu1V9psDXTbkyo9S6vWbk7CWaSoMqRyHOgpHq4GgfnbL9KyZBRVqVwvykeGklP97df6h0bkS0VH
```

Flux will then deploy/manage what it finds in this repo. 