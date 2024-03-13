# HDH API-Documentation

- Base URL: https://staging.dashboard.heidenheim.de/api/
- Endpoint: historical/

The historical endpoint typically returns the same data structure. Here is an example response for the request: `https://staging.dashboard.heidenheim.de/api/historical/?datetime__gte=2024-03-12T09:16:04.498Z&groupIdentifier=b84fcd90-f870-4f75-8793-e7ba7526b07f`

```json
{
  "data": [
    {
      "id": "a5713e95-d456-4bc4-b150-710e455f433c",
      "singleDataPoints": [
        {
          "datetime": "2024-03-13T00:00:02+00:00",
          "value": "11",
          "valueKey": "occupied"
        },
        {
          "datetime": "2024-03-13T00:00:02+00:00",
          "value": "16",
          "valueKey": "bookable"
        }
      ],
      "name": "Heidenheim, Bahnhof, Sammelgarage",
      "labelIdentifier": "unit405",
      "labelName": "Heidenheim, Bahnhof, Sammelgarage",
      "latitude": 48.67968,
      "longitude": 10.156297,
      "groupIdentifier": "b84fcd90-f870-4f75-8793-e7ba7526b07f",
      "misc": {
        "id": "unit405",
        "sum": 27,
        "name": "Heidenheim, Bahnhof, Sammelgarage",
        "latitude": 48.67968,
        "longitude": 10.156297
      }
    }
  ]
}
```

The data contains all entities. Each entity has a id property. The `singleDataPoints` property contains the time series for the entity.

## LabelIdentifier and GroupIdentifier

Every request to the historical endpoint necessitates either a  `groupIdentifier` or the `labelIdentifier` as a query parameter. Both parameters can encompass multiple identifiers separated by commas.

To explore the entities and sensors offered by the smart city, please refer to the [entities csv file](HDH-Entities.csv).

## Filter data

### Filter Time Series by Data Type (valueKey)

The example response above demonstrates that the endpoint furnishes multiple types of values, including data of types `occupied` and `bookable`. To filter the time series for a specific data type, you can append the valueKey argument as a query parameter. Currently, the following valueKey values are recognized:

- status
- vehicles
- current.right_to_left / current.left_to_right
- person.in / person.out
- car.in / car.out
- truck.in / truck.out
- bicycle.in / bicycle.out
- bus.in / bus.out
- van.in / van.out
- motorbike.in / motorbike.out
- level (Waterlevel)
- wind.speed
- temperature
- state (Weather state)
- humidity
- filling (Trash can)
- throwins (Trash can)
- barometric_pressure
- particle.PM10.mass
- ...

Important: Not all sensors deliver all types of `valueKey`. A weather sensor might not detect person.in and person.out.

### Filter by Timerange

To exclusively retrieve data within a specific time range, you can utilize the optional datetime query parameters. Both query parameters are optional, but it's advisable to use `datetime__gte` to enhance the speed of the request.

- `datetime__gte` - filters only data greather or equals than the filter value (e.q. `...&datetime__gte=2024-03-12T09:16:04.500Z`)
- `datetime__lte` - filters only data less or equals than the filter value.