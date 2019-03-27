# API Reference for CS5065-Assignment-1

## Get historical weather data

Gets a list of all dates where weather information is available.

**URL** : `/api/historical/`

**Method** : `GET`

### Success Response

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

## Add weather data

Add weather data. If weather data does not exists it creates new weather data. If weather data does exists, it overwrites the existing weather data.

**URL** : `/api/historical/`

**Method** : `POST`

**Data parameters**

DATE - **string**
- **YYYYMMDD**

TMAX - **float**
TMIN - **float**

**Data example** All fields must be sent.

```json
{
    "DATE":"20180601",
    "TMAX":50,
    "TMIN":34.1
}
```

### Success Response

**Code** : `201 CREATED`

**Content example**

```json
{
    "DATE": "20180601"
}
```

### Error Responses

**Condition** : If fields are missed.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "message": "A parameter is missing."
}
```

**Condition** : If fields are wrong type.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "message": "Incorrect data type"
}
```

**Condition** : If date is wrong format.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "message": "Incorrect date format, should be YYYYMMDD."
}
```