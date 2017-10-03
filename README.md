# phonex-and-gin
Quick experiments w.r.t gin(golang) and phoenix(elixir) based on https://github.com/mroth/phoenix-showdown


# Setup:

## Go-gin app:

Used `dep` already to manage the dependencies with `vendor` directory, so this is completely go-gettable.

  ```
  $ go version
  go version go1.9 linux/amd64
  ```

To run:

  `GOMAXPROCS=4 GIN_MODE=release go run main.go`


## Elixir-phoenix app:

Used `exenv` and running on:

  ```
  $ exenv local
  1.5.2
  ```

To run:

  `MIX_ENV=prod mix phx.server`


---
Now use [wrk](https://github.com/wg/wrk) to compare them:

  `wrk -t20 -c100 -d30S --timeout 2000 "http://127.0.0.1:3000/showdown"`
