# AWI NearRealTime Development Deployment

## Starting

```sh
docker-compose up
```

## Services

The `docker-compose` file contains the following services:

### `sos` - AWI NearRealTime SOS

Available at: http://localhost:3000/service

Example requests:
* http://localhost:3000/service?service=SOS&request=GetCapabilities
* http://localhost:3000/service?service=SOS&version=2.0.0&request=DescribeSensor&procedure=vessel:polarstern
* http://localhost:3000/service?service=SOS&version=2.0.0&request=GetFeatureOfInterest&featureOfInterest=PS100
* http://localhost:3000/service?service=SOS&version=2.0.0&request=GetDataAvailability&procedure=vessel:polarstern&featureOfInterest=PS100&observedProperty=no2
* http://localhost:3000/service?service=SOS&version=2.0.0&request=GetObservation&procedure=vessel:polarstern&featureOfInterest=PS100&observedProperty=no2


### `series-api` - AWI NearRealTime Series SOS Proxy

Available at: http://localhost:3001/api/

### `helgoland` - Current development version of Helgoland

Available at: http://localhost:3002/

### `helgoland-old` - Development version of Helgoland from 10/2017

Available at: http://localhost:3003/

### `frontend` - Nginx Proxy

Nginx frontend intended to act as a gateway to the other services. Not yet working.

Available at: http://localhost:3004

### `sos-db` - NRT SOS database

Postgres database containing an excerpt of the NRT database. Not exposed.

### `series-api-db` - Series SOS Proxy Cache database

Postgres database containing the cache of the Series SOS Proxy. Not exposed.