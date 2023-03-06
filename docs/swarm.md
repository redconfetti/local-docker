# Docker Swarm

I myself decided to the commands from pages 156-159 in
_Docker for Rails Developers_.

I was able to log into my Docker machines using `vagrant ssh docker` and
`vagrant ssh docker2` respectively, and run 'docker -v` each.

## Initializing the Swarm

```shell
$ docker swarm init --advertise-addr 192.168.50.2

Swarm initialized: current node (1y1rzw6x67rdjlovzw244z7g1) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-3hpqeus1kcwhwv5adq0k7a39xuwsm127un41gh2skvxz30ea25-6crmqj5z365jtb8zxphedrauu 192.168.50.2:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.
```
