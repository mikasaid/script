# script
script
Getting Started
The quickest and easiest way to get started with IPinfo is to use one of our official libraries, which are available for many popular programming languages and frameworks. If you'd like to write your own library or interact directly with our API, then the documentation below can help you.

Authentication
Your API token is used to authenticate you with our API and can be provided either as an HTTP Basic Auth username, a bearer token, or alternatively as a token URL parameter.

# With Basic Auth
$ curl -u 802aa6af3e558f: ipinfo.io

# With Bearer token
$ curl -H "Authorization: Bearer 802aa6af3e558f" ipinfo.io

# With token query parameter
$ curl ipinfo.io?token=802aa6af3e558f
It's also possible to use the API without authentication in a more limited capacity.

JSON Response
We try to automatically detect when someone wants to call our API versus view our website, and then we send back the appropriate JSON response rather than HTML. We do this based on the user agent for known popular programming languages, tools, and frameworks. However, there are a couple of other ways to force a JSON response when it doesn't happen automatically. One is to add /json to the URL, and the other is to set an Accept header to application/json:

# Ensure we really get JSON, and not the IPinfo homepage HTML
$ curl ipinfo.io/json
$ curl -H "Accept: application/json" ipinfo.io
IP Address Parameter
The API supports passing in a single IPv4 or IPv6 IP address. Alternatively, if you do not pass in any IP address, we'll return details for the calling address. This allows you to look up your own (or a visitor to your site) IP address details without knowing the IP address in advance.

# Get details for 8.8.8.8
$ curl ipinfo.io/8.8.8.8?token=802aa6af3e558f

# Get details for 2001:4860:4860::8888
$ curl ipinfo.io/2001:4860:4860::8888?token=802aa6af3e558f

# Get details for your own IP address, which'll be included in the response
$ curl ipinfo.io?token=802aa6af3e558f
HTTPS/ SSL
Our API is available over a secure HTTPS connection for all users. Simply add https:// to the request URLs to make the requests secure.

# Get details for your own IP address over HTTPS
$ curl https://ipinfo.io?token=802aa6af3e558f
Rate Limits
Free usage of our API is limited to 50,000 API requests per month. If you exceed that limit, we'll return a 429 HTTP status code to you.

Paid plans come with higher monthly limits, and configurable alerts.

Filtering Responses
You can filter the API response down to specific fields or objects by adding the field or object name to the URL. In the case of a field you'll get it returned in plaintext, and an object will get returned as JSON.

# Get json the org field as plaintext
$ curl ipinfo.io/8.8.8.8/org?token=802aa6af3e558f
AS15169 Google Inc.

# Get just the city as plaintext
$ curl ipinfo.io/8.8.8.8/city?token=802aa6af3e558f
Mountain View

# Get country ISO code as plaintext
$ curl ipinfo.io/8.8.8.8/country?token=802aa6af3e558f
US
JSONP/ CORS Requests
JSONP and CORS are supported, allowing you to use ipinfo.io entirely in client-side code. For JSONP you just need to specify the callback parameter, e.g. http://ipinfo.io/?callback=callback&token=802aa6af3e558f.

Request visitor data using Fetch API (Promise)

fetch("https://ipinfo.io/json?token=802aa6af3e558f").then(
  (response) => response.json()
).then(
  (jsonResponse) => console.log(jsonResponse.ip, jsonResponse.country)
)
Request visitor data using Fetch API (Async/Await)

const request = await fetch("https://ipinfo.io/json?token=802aa6af3e558f")
const json = await request.json()

console.log(jsonResponse.ip, jsonResponse.country)
Request visitor data using JSONP

<script>
  function recordData (data) {
    console.log(data.ip, data.country)



Chessplay
Chess Web Game with Vue JS 3 and WindiCSS

Screenshot

Installation
Clone the repository
git clone https://github.com/zuramai/chessplay
cd chessplay
Install dependencies
npm install
# OR
yarn
Run locally
npm run dev
# OR
yarn dev
Open http://localhost:3000
About
Chess Web Game with Vue JS 3 and Tailwind CSS

chess.ahmadsaugi.com
Topics
vuejs chess windicss
Resources
 Readme
Releases
No releases published
Packages
No packages published
Languages
Vue
81.4%
 
JavaScript
16.7%
 
HTML
1.4%
 
SCSS
0.5%
© 2021 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
