# Docker based examples of UD-Viz

This container illustrates all the examples offered by the
[UD-Viz npm package](https://github.com/VCityTeam/UD-Viz),

Build the docker image with

```bash
docker build -t vcity:ud-viz-examples Context
```

Then run the container e.g. with

```bash
docker run [--detach] UD_VIZ_EXAMPLES_PORT=8080 --rm -t vcity:ud-viz-examples
```

and open a web browser on URL `http://localhost:8080/`

Notes:

- in the above `docker run` command the optionnal `-d` argument requires the
  container to run in detached mode,
- the published port (the `8080` in the above `-p` flag argument of the the 
  `docker run` command) can be changed but has to match with the port given
  (within the URL) when browsing
