Best Jaunt is a flight Booking Platform which also serves as a tour suggestion system.
The main target audience of Best Jaunt would be people who do not mind having long layovers for a cheaper price. 
They can book a tour in the same city as their layover and have a tremendous experience and also pay using matic. We make suggestions based on factors like:-

1)Time of Travel 2)Duration of Layovers
3)Age
4)Interest Areas
5)Previous Experiences
6)Reviews
We plan to add more factors in the future. Our platform can also be integrated on any trip booking site(Cheapflights, uber). 
We also have a feature where you can try out free food samples from different restaurants on your way.
Matic is used to make crypto payments.

---------------------------------------------------------------------------------------------------------------------------------------
Technical Report:

Technologies used--
1)Python
2)Amadeus API (Sponsored)
3)TomTom API (Sponsored)
4)HTML/CSS
5)JavaScript
6)Jinjja
7)Matic

Modules used--
1)Flask 
2)Amadeus Python SDK 
3)TomTom Web SDK
4)ISO8601 Parser
5)Date Parser
6)Json
7)Matic SDK

--------------------------------------------------------------------------------------------------------------------------------------
How is Best Jaunt built?

Flight System:
The Backend of best jaunt is built entirely on Flask. The flight data is fetched in real time from amadeus developer api.
When you search for a flight a GET request is sent to /search which uses the following information to make an API call:-
1)Origin City (string)
2)Destinations City (string)
3)Date of Travel (date)
4)Number of Adults (int)
After the API call is made the response data is stored in a JSON object and is passed on to the rendered html template. 
Here Jinjja is used to display the required information from the json dictionary. JSON dictionary primarily includes:-

a)IATA Codes of: 
1)Origin City
2)Layover Cities 
3)Destination City

b)Time and Dates (ISO 8601 Format) of:-
1)Departure at Origin 
2)Arrival at Layover City(s) 
3)Departure at Layover City(s) 
4)Arrival at Destination
5)Flight Number
6) Carrier Code

c)Above Information is used to derive the following:
1)Name of the City: a)Manually made a Dictionary of known City's and their IATA Codes b)Used IATA codes to map with the City names
2)Duration of Flight
3)Duration of Layover
4)Duration of Each Flight

----------------------------------------------------------------------------------------------------------------------------------------

Tour System:

We used Points of Interest API (available from both Amadeus and TomTom) to point out most visited places in the given city and made a
calculated route usingTomTom's API using time constraints and then the Map is displayed using JavaScript on a different page.

----------------------------------------------------------------------------------------------------------------------------------------

How to use it?

a)fork this repository or clone it from https://github.com/iam-abbas/Stellio.git
b)installing following using PIP
c)amadeus
d)iso8601
e)twilio
f)json
g)flask
h)Get the following APIs:-
i)Amadeus Free API
j)Twilio Free Trial Whatsapp API
k)TomTom Free API
l)Update main.py with your API keys where it is mentioned
m)For TomTom update it on /templates/map.html

Now just run it using python3 main.py
