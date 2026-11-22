# ${{ values.name }}

Scaffolded by the Backstage golden-path template `go-service`.

## Run it

```bash
go run .
curl localhost:8080/healthz
```

## Endpoints

- `GET /healthz` — liveness/readiness probe
- `GET /` — service greeting
