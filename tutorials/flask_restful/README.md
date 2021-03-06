# Flask-restful demo api

1) run `api.py`
2) server should be running at localhost (`127.0.0.1:5110`), config can be changed from api.py main
3) perform http GET requests at `127.0.0.1:5110/api/restaurants`

    The restaurants endpoint includes 2 non-required parameters
    
    * `area` (str) - the area of the restaurant 
    * `min_rating` (float) - the minimum average rating of the restaurant. If the `min_rating` parameter is negative,
     a `400 - BAD REQUEST` error code is returned alongside a message. 
     
4) perform http POST requests at `127.0.0.1:5110/api/reviews` to add new reviews in reviews.txt

    The reviews endpoint includes 2 required parameters
    
    * `text` (str) - the review text
    * `restaurant_name` (str) - the name of the restaurant

Example requests

* `GET 127.0.0.1:5110/api/restaurants` - Returns all the restaurants (from restaurants.json)
* `GET 127.0.0.1:5110/api/restaurants?area=brooklyn` - Returns all restaurants in brooklyn
* `GET 127.0.0.1:5110/api/restaurants?area=brooklyn&min_rating=1`- Returns all restaurants in brooklyn with a
minimum rating of 1
* `GET 127.0.0.1:5110/api/restaurants?min_rating=-10` - 400 BAD REQUEST {"Error": "min_rating cannot be a negative value"}
* `POST 127.0.0.1:5110/api/reviews?text=This is the best restaurant&restaurant_name=Some restaurant` - {
    "status": "Review saved successfully"}