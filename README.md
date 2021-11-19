# COMP3040-A3-Group

## Description
* Finding Aurora API lets us find information about past and future northern lights by taking inputs such as location and time. The northern lights, aka Aurora, are mesmerizing waves of light that are known for their beauty. This API provides us information such as the KP index, which describes characteristics of the current aurora. 


## Endpoints

### By location
```auroraapi.org/location```

#### Parameters
* **lat** (float): The latitude of the location
* **long** (float): The longitude of the location

**NOTE:** `lat` and `long` must both be present, or neither present for current location.

#### Returns
Returns an array of [Aurora Events](#aurora-event) of length 1 denoting the next or current event for the given location.

### By time
```auroraapi.org/time```

#### Parameters
* **time** (int): The time an aurora occurred, formatted as a UTC Unix timestamp.

#### Returns
Returns an array of [Aurora Events](#aurora-event).

### Get photos
```auroraapi.org/photo```

#### Parameters
* **lat** (float): The latitude of the location
* **long** (float): The longitude of the location

**NOTE:** `lat` and `long` must both be present, or neither present for current location.

#### Returns
Returns a [Photo object](#photo).

## Resources
* time: UTC Unix Timestamp
* length: Number of seconds, -1 if unknown
* kp: Integer ranging from 0-9

### Aurora Event
```json
[
    {
        "time": 1637280856,
        "location": {
            "lat": 49.8951,
            "long": 97.1384
        }
        "length": 20,
        "kp": 2
    },
]
```


### Photo
```json
{
    "url": "https://imagesite.com/image.png",
    "time": 1637280856,
    "location": {
        "lat": 49.8951,
        "long": 97.1384
    }
    "kp": 2
}
```

## Sample Requests

### Location
#### Request
`https://auroraapi.org/location?lat=49.8951&long=97.1384`

#### Response
```json
[
    {
        "time": 1637280856,
        "location": {
            "lat": 49.8951,
            "long": 97.1384
        }
        "length": 20,
        "kp": 2
    }
]
```

### Time
#### Request
`https://auroraapi.org/time?time=1637280856`

#### Response
```json
[
    {
        "time": 1637280856,
        "location": {
            "lat": 49.8951,
            "long": 97.1384
        }
        "length": 20,
        "kp": 2
    }
]
```

### Photo
#### Request
`https://auroraapi.org/photo?lat=49.8951&long=97.1384`

#### Response
```json
{
    "url": "https://imagesite.com/image.png",
    "time": 1637280856,
    "location": {
        "lat": 49.8951,
        "long": 97.1384
    }
    "kp": 2
}
```
