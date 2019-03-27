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

## Get historical weather data by date

Gets the weather data for one day.

**URL** : `/api/historical/<date>`

**Method** : `GET`

### Success Response

**Code** : `200 OK`

**Content examples**

```json
{
    "DATE": "20180601",
    "TMAX": 89.1,
    "TMIN": 51.3
}
```
### Error Responses

**Condition** : If date is wrong format.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "message": "Incorrect date format, should be YYYYMMDD."
}
```

**Condition** : If date does not exist.

**Code** : `404 NOT FOUND`

**Content example**

```json
{
    "message": "Weather information for this date does not exist."
}
```

## Delete historical weather data by date

Deletes the weather data for one day.

**URL** : `/api/historical/<date>`

**Method** : `DELETE`

### Success Response

**Code** : `204 NO CONTENT`

**Content examples**

```json
```
### Error Responses

**Condition** : If date is wrong format.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "message": "Incorrect date format, should be YYYYMMDD."
}
```

**Condition** : If date does not exist.

**Code** : `404 NOT FOUND`

**Content example**

```json
{
    "message": "Weather information for this date does not exist."
}
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

## Get 7-day forecast from start date

Gets the 7-day forecast starting from specified date.

**URL** : `/api/forecast/<date>`

**Method** : `GET`

### Success Response

**Code** : `200 OK`

**Content examples**

```json
[
    {
        "DATE": "20180601",
        "TMAX": 82.76666666666667,
        "TMIN": 58.98333333333334
    },
    {
        "DATE": "20180602",
        "TMAX": 64.4,
        "TMIN": 57.5
    },
    {
        "DATE": "20180603",
        "TMAX": 80.7,
        "TMIN": 71.6
    },
    {
        "DATE": "20180604",
        "TMAX": 84.6,
        "TMIN": 66.3
    },
    {
        "DATE": "20180605",
        "TMAX": 84.7,
        "TMIN": 64
    },
    {
        "DATE": "20180606",
        "TMAX": 94.6,
        "TMIN": 70.4
    },
    {
        "DATE": "20180607",
        "TMAX": 86.4,
        "TMIN": 68.1
    }
]
```
### Error Responses

**Condition** : If date is wrong format.

**Code** : `400 BAD REQUEST`

**Content example**

```json
{
    "message": "Incorrect date format, should be YYYYMMDD."
}
```