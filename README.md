# VyOS Container Images
This repository contains a simple workflow to automatically build VyOS docker images. It pulls the official VyOS build scripts and automatically builds the current LTS and nightly. It can be ran with:
 ```docker run -v /lib/modules:/lib/modules --privileged --name vyos_inside_docker -d ghcr.io/np22-jpg/vyos:current```

 Then, you can connect to the container with:
```docker exec -it vyos_inside_docker su vyos```

You can read more about VyOS in docker [here](https://github.com/vyos/vyos-build/tree/current/docker-vyos).

## Verification
These images are signed with sigstore cosign. They can be verified by downloading `cosign.pub` and running the following:

```cosign verify --key cosign.pub ghcr.io/np22-jpg/vyos```