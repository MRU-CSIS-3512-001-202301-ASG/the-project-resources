# API Details

All API endpoints must return a valid JSON response.

## Dead Drop API

### `/api/ddrop.php`

#### Description
Lists the city, country, and lat/long values of all currently active dead drops.

#### Query Parameters
None

#### Example Response

```json
{
  "total_count":2,
  "drops":[
    {
      "city":"Nagasaki",
      "country":"Japan",
      "lat":32.746566,
      "long":129.881818
    },
    {
      "city":"Fort Assiniboine",
      "country":"Canada",
      "lat":54.334761,
      "long":-114.774803
    }
  ]
}
```

### `/api/ddrop.php?city={city_id}`

#### Description
Lists the number of currently active drops in a given city.

#### Query Parameters
`city_id` _integer_  **Required**

The id of the city to query.

#### Example Response

```json
{
  "num_drops":4
}
```
