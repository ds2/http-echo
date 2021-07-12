Run

    export GOPATH=$(pwd)/gopath
    go mod tidy
    go build -o tmp/http-echo

To package, run:

    docker build -t http-echo:latest --rm -f docker/scratch/Dockerfile .
    docker run -it --rm http-echo:latest
