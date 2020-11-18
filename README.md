# Nomad

This is nomad cheat sheet, I use nomad in my current project and did not find any good cheat sheet so here is one..

## Download

https://www.nomadproject.io/downloads

## Connect remotely to nomad

export NOMAD_ADDR="http://192.168.99.100:4646"

## Create nomad windows service
```bash
sc create "Nomad" binPath="S:\Tools\HashiCorp\nomad.exe agent -config=S:\Tools\HashiCorp\configs\client-server-combined-file.hcl start= auto
```

## Nomad gui
```bash
http://192.168.91.10:4646/ui/jobs
```

## Start agent
```bash
nomad agent -dev                  # client and server
nomad agent -config server.hcl    # server only
nomad agent -config client.hcl    # client only
nomad agent -config client-server-combined-file.hcl
```

## Inspect clients
```bash
nomad node status
```
## Inspect servers
```bash
nomad server members
nomad server members -detailed
```
## Plan, run and stop job
```bash
nomad plan jobname or jobfile
nomad run jobname or jobfile
nomad stop jobname or jobfile
nomad job stop -detach jobname or jobfile
nomad job stop -purge jobname
```
## Get job status
```bash
nomad status job
nomad status -evals job
```
## Get evaluation status
```bash
nomad eval-status <evalid>
Get allocation status
nomad alloc-status <allocid>
```
## Get allocation logs
```bash
nomad logs <allocid>
nomad logs -f <allocid>
nomad logs -stderr <allocid>
nomad logs -f -stderr <allocid>
```
## Start service
```bash
sudo systemctl restart nomad
```
## check logs
```bash
journalctl -u nomad
```

