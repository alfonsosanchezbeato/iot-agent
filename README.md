[![Build Status][travis-image]][travis-url]
[![Go Report Card][goreportcard-image]][goreportcard-url]
[![codecov][codecov-image]][codecov-url]
# IoT Agent

The IoT Agent enrolls a device with the [IoT Identity](https://github.com/CanonicalLtd/iot-identity) service and 
receives credentials to access the MQTT broker. Via MQTT, it establishes communication with
an [IoT Management](https://github.com/CanonicalLtd/iot-management) service, so the device can be remotely monitored and managed over a
secure connection. The state of the device is mirrored in the cloud by the [IoT Device Twin](https://github.com/CanonicalLtd/iot-devicetwin) service.

The agent is intended to operate on a device running Ubuntu or Ubuntu Core with snapd enabled. 
The device management features are implemented using the snapd REST API.

 ## Design
  ![IoT Management Solution Overview](docs/IoTManagement.svg)
  

## Build
The project uses vendorized dependencies using govendor. Development has been done on minimum Go version 1.12.1.
```bash
$ go get github.com/CanonicalLtd/iot-agent
$ cd iot-agent
$ ./get-deps.sh
$ go build ./...
```

## Run
```bash
go run cmd/agent/main.go -help
  -credentials string
        The full path to the credentials file (default ".secret")
  -url string
        The URL of the Identity Service (default "http://localhost:8030/")
```

## Contributing
Before contributing you should sign [Canonical's contributor agreement](https://www.ubuntu.com/legal/contributors), it’s the easiest way for you to give us permission to use your contributions.

[travis-image]: https://travis-ci.org/CanonicalLtd/iot-agent.svg?branch=master
[travis-url]: https://travis-ci.org/CanonicalLtd/iot-agent
[goreportcard-image]: https://goreportcard.com/badge/github.com/CanonicalLtd/iot-agent
[goreportcard-url]: https://goreportcard.com/report/github.com/CanonicalLtd/iot-agent
[codecov-url]: https://codecov.io/gh/CanonicalLtd/iot-agent
[codecov-image]: https://codecov.io/gh/CanonicalLtd/iot-agent/branch/master/graph/badge.svg