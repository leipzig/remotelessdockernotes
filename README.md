# remotelessdockernotes
notes on localizing remote dependencies for reproducible docker builds

## Inspiration
- https://twitter.com/smllmp/status/1542131074339422212 
- https://twitter.com/tallphil/status/1570525478825644038

## Rationale
Docker is not a panacea for reproducibility. Docker images are stable binary freezes, but Dockerfiles often fetch remote hyperlinks that can easily change or disappear. The goal here is to intercept any files the docker build process accesses from the internet and save them locally, then fool the build process into using those local versions on subsequent builds. Some processes also fetch dependencies at runtime, so a more extended approach may be required there.
.
## logging network access
### Unix
- iftop
- lsof
- https://www.digitalocean.com/community/tutorials/how-to-sandbox-processes-with-systemd-on-ubuntu-20-04

### Running containers
- https://byteplumbing.net/2018/01/inspecting-docker-container-network-traffic/
- https://docs.docker.com/config/containers/logging/configure/

## How to proxy local files as if remote
- https://github.com/kurron/docker-charles-proxy

## Related projects
- https://reproducible-builds.org/tools/
- ReproZip
