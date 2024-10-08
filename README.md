# ARCHIVED

This project is no longer maintained and will not receive any further updates. If you plan to continue using it, please be aware that future security issues will not be addressed.

# AWI NearRealTime Development Deployment

## Starting

```sh
docker-compose up
```

## Services

The [`docker-compose.yml`](https://github.com/52North/awi-nearrealtime/blob/master/docker-compose.yml) file contains the following services:

### `sos` - [AWI NearRealTime SOS](https://github.com/52North/awi-nearrealtime-sos)

Available at: http://localhost:3000/sos/service

Example requests:
* http://localhost:3000/sos/service?service=SOS&request=GetCapabilities
* http://localhost:3000/sos/service?service=SOS&version=2.0.0&request=DescribeSensor&procedure=vessel:polarstern
* http://localhost:3000/sos/service?service=SOS&version=2.0.0&request=GetFeatureOfInterest&featureOfInterest=PS100
* http://localhost:3000/sos/service?service=SOS&version=2.0.0&request=GetDataAvailability&procedure=vessel:polarstern&featureOfInterest=PS100&observedProperty=no2
* http://localhost:3000/sos/service?service=SOS&version=2.0.0&request=GetObservation&procedure=vessel:polarstern&featureOfInterest=PS100&observedProperty=no2


### `series-api` - [AWI NearRealTime Series SOS Proxy](https://github.com/52North/awi-nearrealtime-series-proxy)

Available at: http://localhost:3000/api/

### `helgoland` - [Current development version of Helgoland](https://github.com/52North/helgoland/tree/feature/angularUpgrade)

Available at: http://localhost:3000/

### `frontend` - Nginx Proxy

Nginx frontend intended to act as a gateway to the other services.

Available at: http://localhost:3000/

### `sos-db` - [NRT SOS database](https://github.com/52North/awi-nearrealtime-example-db)

Postgres database containing an excerpt of the NRT database. Not exposed.

### `series-api-db` - Series SOS Proxy Cache database

Postgres database containing the cache of the Series SOS Proxy. Not exposed.
