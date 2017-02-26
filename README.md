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
