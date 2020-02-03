## Introduction (Business Problem)
Toronto is home to a large thriving culinary scene, seeing as it is the largest city in Canada with a population of over 6 million. If a restaurateur wanted to establish their very own breakfast restaurant in Toronto, then which neighbourhood would be best suited for its success? In other words, we wish to determine which neighbourhoods in Toronto have the highest unmet demand for breakfast.

## Data Description
Foursquare's API will be used to gather data on the current selection of breakfast restaurants in Toronto. Together with web scraping from <https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M>, we can retrieve data about the neighbourhoods of Toronto and merge this data with Foursquare's retrieved data about breakfast restaurants. 

Additionally, the Traffic Signal Vehicle and Pedestrian Volumes dataset from <https://open.toronto.ca/dataset/traffic-signal-vehicle-and-pedestrian-volumes/> will be used to determine the average peak traffic flow through the neighbourhoods. This dataset consists of 8 peak hour vehicle and pedestrian volume counts collected at intersections where there are traffic signals. It will be vital in determining where there is a large amount of traffic in certain neighbourhoods that have unmet demand for breakfast restaurants. Using Folium, a map can be built of traffic volume using some sort of regressor like K-Nearest Neighbours. This visualization will be of great help when we cross-reference it to a map of the various neighbourhoods. 

In the future, some demographics data about the neighbourhoods' populations from <https://open.toronto.ca/dataset/neighbourhood-profiles/> can be looked at as well. My initial guess is that highly populated residential areas are just as important as high-traffic areas in determining where breakfast restaurants would be most popular.

## Methodology
### Exploratory Data Analysis

<iframe src="https://github.com/Griffin-Thomas/Applied_Data_Science_Capstone/first_map.html" height="650" width="100%"></iframe>