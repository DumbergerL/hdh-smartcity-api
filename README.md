# AA-HDH SmartCity API

Aalen and Heidenheim are jointly developing their cities into smart cities. The long-term plan is to [create a data platform](https://www.aahdhgemeinsamdigital.de/massnahmen/massnahme-5) to break down data silos. As long as this platform has not yet been realised, this API wrapper tool will help to retrieve the data from the dashboards. 

> [!IMPORTANT]
> The reverse engineering of unofficial web APIs is highly experimental. The API can change constantly. Even if this project is intended to guarantee a certain degree of stability, changes cannot be ruled out.

- [Dashboard Aalen](https://aalen-dashboard.de/)
- [Dashboard Heidenheim](https://staging.dashboard.heidenheim.de/)

## API Example Reqeusts

To test API endpoints, I use [Bruno](https://github.com/usebruno/bruno) instead of e.g. Postman because the sample requests can be versioned in git. The sample requests are stored in the `bruno-api` folder.

## API Documentation

See the inofficial API Documentation:

- [API Doucmentation Heidenheim](HDH-API-Documentation.md)
- [API Doucmentation Aalen](AA-API-Documentation.md) (incomplete)

## Map with Sensors

Each sensor in the Smart City has a geographical position. I've generated a map that visualizes all sensors. The project source is in the `hdh-sensor-map` folder:

[https://dumbergerl.github.io/hdh-smartcity-api/hdh-sensor-map/](https://dumbergerl.github.io/hdh-smartcity-api/hdh-sensor-map/)

![Thumbnail Map](hdh-sensor-map/thumbnail.png)

## Traffic Heat Map

Animation of traffic for one week (Folder: `hdh-traffic-heat-map`).

[https://dumbergerl.github.io/hdh-smartcity-api/hdh-traffic-heat-map/](https://dumbergerl.github.io/hdh-smartcity-api/hdh-traffic-heat-map/)