[![GoDoc](https://img.shields.io/badge/go-documentation-blue.svg?style=flat-square)](https://godoc.org/github.com/khezen/kraken-go-api-client)
[![Build Status](http://img.shields.io/travis/Khezen/kraken-go-api-client.svg?style=flat-square)](https://travis-ci.org/Khezen/kraken-go-api-client) [![codecov](https://img.shields.io/codecov/c/github/Khezen/kraken-go-api-client/master.svg?style=flat-square)](https://codecov.io/gh/Khezen/kraken-go-api-client)
[![Go Report Card](https://goreportcard.com/badge/github.com/khezen/kraken-go-api-client?style=flat-square)](https://goreportcard.com/report/github.com/khezen/kraken-go-api-client)

# Kraken Go API Client

A simple API Client for the [Kraken](https://www.kraken.com/ "Kraken") Trading platform.

## Example usage:

```go
package main

import (
	"fmt"
	"log"

	"github.com/khezen/kraken-go-api-client"
)

func main() {
	api := krakenapi.New("KEY", "SECRET")
	result, err := api.Query("Ticker", map[string]string{
		"pair": "XXBTZEUR",
	})

	if err != nil {
		log.Fatal(err)
	}

	fmt.Printf("Result: %+v\n", result)

	// There also some strongly typed methods available
	ticker, err := api.Ticker(krakenapi.XXBTZEUR)
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(ticker.XXBTZEUR.OpeningPrice)
}
```
