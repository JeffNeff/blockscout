# EthOne Blockscout

## Quick Deploy

```bash
git clone https://github.com/etheronechain/blockscout.git
cd blockscout/docker-compose/
docker compose up -d
```

## Services Rendered:

* Blockscout: http://localhost4000
* Smart Contract Verifier: http://localhost:8043
* Redis: http://localhost6379
* Postgres: http://localhost5432

## Bundled Stack

```bash
cd docker-compose
docker build -t myimage .
docker run -it --rm -v /var/run/docker.sock:/var/run/docker.sock:ro -v docker-compose.yml:/docker-compose.yml myimage 
```
