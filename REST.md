# API Reference for CS5065-Assignment-1

## Get historical weather data

Get the details of the currently Authenticated User along with basic
subscription information.

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
    },
    ...
```

## Notes

* If the User does not have a `UserInfo` instance when requested then one will
  be created for them.