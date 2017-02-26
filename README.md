# Random Name Generator in Golang
## Overview
Creates random names, and a timestamp, based on the Docker random name generator. Plan is to use this to fill a SQL database with data.

## Usage
Build the package with `go build random_names.go` and then use the command line parameters below to control behaviour:

* `-loops` - the number of names/timestamps to generate
* `-sleepLen` - the length of time to sleep between iterations (in milliseconds)

## Example Output

```
~:Golang root$ ./random_names -loops=4 -sleepLen=1000
2017-02-26T13:31:34.099245275Z 		 nervous bassi
2017-02-26T13:31:35.10454553Z 		 reverent bardeen
2017-02-26T13:31:36.108942539Z 		 distracted noether
2017-02-26T13:31:37.114285284Z 		 suspicious khorana
~:Golang root$
```

## Creating a containerised version
```
CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o random_names random_names.go
```
```
docker build -t timhynes/name_gen -f Dockerfile.scratch .
```
This will create a Linux executable container named timhynes/name_gen:

```
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
timhynes/name_gen     latest              436a832943c8        12 seconds ago      1.77 MB
```
This can then be executed with `docker run timhynes/name_gen`:
```
~:Golang root$ docker run timhynes/name_gen
2017-02-26T14:07:59.111767032Z 		 clever khorana
2017-02-26T14:07:59.121976978Z 		 inspiring knuth
2017-02-26T14:07:59.132212095Z 		 elated galileo
2017-02-26T14:07:59.142849257Z 		 reverent perlman
2017-02-26T14:07:59.153295436Z 		 infallible mahavira
2017-02-26T14:07:59.163982342Z 		 inspiring bhabha
2017-02-26T14:07:59.17424263Z 		 compassionate chandrasekhar
2017-02-26T14:07:59.184951012Z 		 compassionate edison
2017-02-26T14:07:59.197533573Z 		 stupefied sammet
2017-02-26T14:07:59.207860486Z 		 heuristic swanson
~:Golang root$ 
```
