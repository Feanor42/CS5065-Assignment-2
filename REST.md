# API Reference for CS5065-Assignment-1

## Get historical weather data

Gets a list of all dates where weather information is available.

**URL** : `/api/historical/`

**Method** : `GET`

**Auth required** : NO

**Permissions required** : None

## Success Response

**Code** : `200 OK`

**Content examples**

```json
[
    {
        "DATE": "20130101"
    },
    {
        "DATE": "20130102"
    },
    {
        "DATE": "20130103"
    }
]
```