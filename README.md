# Django-Weather-Project
Django weather web app that uses OpenWeatherMap APIs to geocode user-entered locations and display current weather data including temperature, precipitation, humidity, and wind speed.


Function Prototype/App Name	Description of its purpose

function get_coordinates within weather/views.py	This converts city names into coordinates using the geocoding API from OpenWeatherMap. This is because OpenWeatherMap uses this highly detailed grid system that prefers coords over city names for better precision. Also, the city name search feature was deprecated.

function weather_display within weather/views.py	This is the meat of the program. Once the user sends data, it scrapes the weather data based on the coords obtained in the previous function. It sends HTTP requests based on the parameters specified by the user. It then scrapes the data from the .json file type that the OpenWeatherMap API returns. It handles any HTTP errors and then creates a dictionary from the obtained variables. Finally it renders this to my weather.html file.

Weather.html	My html file is the front end to my website, it’s what the user sees. This is my first semester ever touching HTML so I kept it pretty basic. It takes the form var from my weather_display function (it was passed there, it was originally defined in forms.py to form the entry fields on the site. Once it has that, it checks if the data has been scraped successfully (i.e. is not equal to None) and then it displays it.

Settings.py	Had to add the name of my app ‘weather’ to the INSTALLED_APPS var.
Forms.py	This holds my LocationForm class where I define what the entry fields will look like on the site. I pass this class into views.py so that I can create an instance of it to pass to the HTML template using the context dictionary which I had titled info_to_pass. In the HTML file, the line {{ form.as_p }} rendered each form field into a <p> (paragraph) element.

Screenshots:
1.	Colorado Springs, CO, USA
 
2.	Winter Park, CO, USA

