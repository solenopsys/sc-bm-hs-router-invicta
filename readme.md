# Docker
docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -t registry.local/hs-router:latest --push .

# Helm
helm package .\install

## Registry width helm cli
helm push hs-router-0.1.0.tgz  oci://helm.local --insecure-skip-tls-verify

## Registry width direct http
curl --data-binary "@hs-router-0.1.0.tgz" http://helm.local/api/charts

# Env Vars
- server.Host=localhost
- server.Port=8080
- nodes.Port=9999


 


 
 
