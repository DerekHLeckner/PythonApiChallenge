# Python API Homework - What's the Weather Like?

## Background

This challenge uses Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Naturally, it gets hotter, but the goal is to prove it.

![Equator](Images/equatorsign.png)

## Part I - WeatherPy

In this example, we write a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish are utilizing a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api).

The first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, we add a sentence or two explaining what the code is and analyzing.

The second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, we explain what the linear regression is modeling such as any noticable relationships and any other analysis.


### Part II - VacationPy

In this part of the challenge, we use jupyter-gmaps and the Google Places API to create a heat map that displays the humitidy for every city we reviewed earlier.

  ![heatmap](Images/heatmap.png)

* We narrow down the DataFrame to find the cities with ideal weather conditions. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * We drop any rows that don't contain all three conditions. 

* Using Google Places API, we find the first hotel for each city located within 5000 meters of the proposed coordinates.

* We plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)
