# Hiding API keys with a proxy server

Credit to [Brad Traversy](https://traversymedia.com), a great and awesome contributor to dev community
I built this project by following his [YouTube tutorial](https://youtu.be/ZGymN8aFsv4)


## Cool things I learned
### [Needle npm](https://www.npmjs.com/package/needle)
A very light weight HTTP client for making request from serve to public API. Needle will return a promise so Async-Await is required to handle it.

### [EXPRESS rate limiter](https://www.npmjs.com/package/express-rate-limit)
Use to limit repeated requests to public APIs and/or endpoints such as password reset. Rate limiting is a very powerful feature for securing backend APIs from malicious attacks and for handling unwanted streams of requests from users. In general terms, it allows us to control the rate at which user requests are processed by our server.

### [apicache](https://www.npmjs.com/package/apicache)
To store copies of frequently accessed API data in several places along the request-response path. So that, next time, when the client requests the same information, instead of sending a new API request, it will give the information from the local memory.

##### Personal note: deployed to heroku@akitadrillingAcct





## Usage
Server used for hiding API keys, rate limiting and caching. This uses the [OpenWeather API](https://openweathermap.org/api) but you can easily change it to whatever public API you are using

### Install dependencies

```js
npm install
```

### Run on http://localhost:5000

```js
npm run dev
```

### Add public API info

Add an **.env** file and set the variables as below:

If the public API URL is **https://api.openweathermap.org/data/2.5/weather?q={city}&appid={APIkey}**

- API_BASE_URL = "https://api.openweathermap.org/data/2.5/weather"
- API_KEY_NAME = "appid"
- API_KEY_VALUE = "YOUR API KEY"

You can add on any other query params as needed when hitting the /api endpoint such as https://yourdomain/api?q=Ottawa without having to add your key in the client

- Add new routes as you see fit
- Change rate limiting and caching to desired values


