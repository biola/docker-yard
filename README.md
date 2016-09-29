# Docker Yard

This docker image is used for running yard doc commands and a yard server locally.
See http://yardoc.org/ for more details.


## Usage

```
docker run --rm -it --name yard -p 8808:8808 -v /path/to/project:/app biola/yard
```

* `--rm` Destroy the container after the process exits.
* `-it` Run interactively.
* `--name` Names the container so it is easy to reference and remove later.
* `-p` Map the default port the yard server users to the host.
* `-v` You need to mount the files you want to compile documentation from to `/app` in the container.
* `biola/yard` The name of the image you want to run.

By default the image runs the following command

```
yard server --reload
```

This will start up a server on port `8808` and will watch the files for changes and rebuild the docs automatically if it detects any changes.

You may instead run whatever command you want by appending the command to the very end of the `docker run` statement.

Once the server is running you can visit the doc page in your browser http://localhost:8808/.
