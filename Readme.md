# Docker based examples of UD-Viz

This container illustrates all the examples offered by the
[UD-Viz npm package](https://github.com/VCityTeam/UD-Viz),

Build the docker image with

```bash
docker build [-build-arg checkoutName=master] -t vcity:ud-viz-examples Context
```

Then run the container e.g. with

```bash
docker run -p 0.0.0.0:8080:8000/tcp [--detach] --rm -t vcity:ud-viz-examples
```

and open a web browser on URL `http://localhost:8080/`

Notes:

- you can specify the branch or a commit in the build arg `checkoutName` (*default = master*) 
- in the above `docker run` command the optionnal `--detach` argument requires the
  container to run in background (detached mode),
- the published port (the `8080` in the above `-p` flag argument of the the
  `docker run` command) can be changed but has to match with the port given
  (within the URL) when browsing
