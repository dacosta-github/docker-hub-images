Dockerfile

Build an image from the Dockerfile and assign it a name.

```$ docker build -t postgresql . ```

Run the PostgreSQL server container (in the foreground):

$ docker run --rm -P --name pg_test postgresql