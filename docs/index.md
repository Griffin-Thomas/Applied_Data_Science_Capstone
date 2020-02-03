## Introduction (Business Problem)
Toronto is home to a large thriving culinary scene, seeing as it is the largest city in Canada with a population of over 6 million. If a restaurateur wanted to establish their very own breakfast restaurant in Toronto, then which neighbourhood would be best suited for its success? In other words, we wish to determine which neighbourhoods in Toronto have the highest unmet demand for breakfast.

## Data Description
[Foursquare](https://foursquare.com/)'s API will be used to gather data on the current selection of breakfast restaurants in Toronto. Together with web scraping from [Wikipedia's List of Postal Codes of Canada](https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M), we can retrieve data about the neighbourhoods of Toronto and merge this data with Foursquare's retrieved data about breakfast restaurants:

| Postcode | Borough      | Neighbourhood    |
|----------|--------------|------------------|
| M1A      | Not assigned | Not assigned     |
| M6A      | North York   | Lawrence Heights |
| M6A      | North York   | Lawrence Manor   |
| M9A      | Queen's Park | Not assigned     |

Additionally, the [Traffic Signal Vehicle and Pedestrian Volumes](https://open.toronto.ca/dataset/traffic-signal-vehicle-and-pedestrian-volumes/) dataset will be used to determine the average peak traffic flow through the neighbourhoods. This dataset consists of volume counts collected at intersections where there are traffic signals: 

| Column Name                 | Description                                      |
|-----------------------------|--------------------------------------------------|
| Main                        | Main street name                                 |
| Latitude                    | Latitude geo-coordinate                          |
| Longitude                   | Longitude geo-coordinate                         |
| 8 Peak Hr Vehicle Volume    | Total vehicle volume between 7:30am to 6:00pm    |
| 8 Peak Hr Pedestrian Volume | Total pedestrian volume between 7:30am to 6:00pm |

It will be vital in determining where there is a large amount of traffic in certain neighbourhoods that have unmet demand for breakfast restaurants. Using [Folium](https://python-visualization.github.io/folium/), a map can be built of traffic volume using some sort of regressor like [K-Nearest Neighbours](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html) or [Radius Neighbours](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.RadiusNeighborsRegressor.html). This visualization will be of great help when we cross-reference it to a map of the various neighbourhoods. 

In the future, some demographics data about the neighbourhoods' populations from [Toronto's Open Data Portal](https://open.toronto.ca/dataset/neighbourhood-profiles/) can be looked at as well. My initial guess is that highly populated residential areas are just as important as high-traffic areas in determining where breakfast restaurants would be most popular.

## Methodology
### Data Wrangling
Once the Wikipedia List of Postal Codes of Canada table was retrieved as a dataframe, it was immediately recognized that there were several entries with an unassigned borough. Hence, these entries were excluded. As for any unassigned neighbourhood values, they were replaced with their respective borough. And since more than one neighbourhood can exist in one postal code area, any of these relevant rows will be combined into one row with the neighbourhoods comma-separated. 

Lastly, latitude and longitude coordinates were added as additional columns using [Geocoding with ArcGIS](https://developers.arcgis.com/features/geocoding/):

| Postcode | Borough     | Neighbourhood                          | Latitude  | Longitude  |
|----------|-------------|----------------------------------------|-----------|------------|
| M1B      | Scarborough | Rouge, Malvern                         | 43.811525 | -79.195517 |
| M1C      | Scarborough | Highland Creek, Rouge Hill, Port Union | 43.785665 | -79.158725 |
| M1E      | Scarborough | Guildwood, Morningside, West Hill      | 43.765815 | -79.175193 |
| M1G      | Scarborough | Woburn                                 | 43.768369 | -79.217590 |

With these coordinates, we can visualize these neighbourhoods on a map of Toronto using Folium!
<iframe src="https://griffin-thomas.github.io/Applied_Data_Science_Capstone/figs/first_map.html" height="650" width="100%"></iframe>

### Exploratory Data Analysis

## Results

## Discussion

## Conclusion

