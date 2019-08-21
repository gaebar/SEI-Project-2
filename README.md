# SEI Project 2 - Retrieves a map of locations of potential destination for digitals nomads using live streaming webcams.
See the website online at http://digital-nomad-ga.herokuapp.com/

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project #2: Reacathon
See the website online at


![ga_cog_large_red_rgb](https://cloud.githubusercontent.com/assets/40461/8183776/469f976e-1432-11e5-8199-6ac91363302b.png)
​
# Software Engineering Immersive: Project 2
Digital Nomad Hub was the second project during the General Assembly Software Engineering Immersive course (Week 5). The project was made in collaboration with Katarzyna https://github.com/kasiaaguti
​
### Timeframe & Team
> 48h, pair programming

### The Brief
Build a React application that consumes a public API.
Have several components - At least one classical and one functional.
The app should include a router - with several "pages".
Have semantically clean HTML.
Be deployed online and accessible to the public.
Work in pairs.
​
### Technologies
* React
* Axios
* Insomnia
* Webpack
* HTML5
* CSS
* Bulma
* Teletype
* Heroku

### Deployment
The website is deployed on Heroku and it can be found here: http://digital-nomad-ga.herokuapp.com/
___

## Website Summary
We had to render an app that retrieves data from a public API in an interesting and engaging manner. We had just under 48 hours to achieve this goal, making it extremely time-sensitive. We chose to create a web app called Digital Nomad Hub, which allows users to retrieve a map of locations of potential destination for digitals nomads, using the Mapbox and Rapid webcams APIs.

My part in the project included creating a Mapbox API integration, display the results on the map and general styling of the map.

___
## Approach
As this was a pair coded 'reactathon' with a very limited timeframe, we chose was to focus on functionality. For styling we used Bulma which was very helpful.
Most of our coding was done on one laptop, so we discussed each piece of code and the best approaches. We also used the Teletype team coding tool.

### Process
The core idea was to used Webcamstravel API https://webcamstravel.p.rapidapi.com/ and render it on a map (for which we used Mapbox). Webcam API gave us access to public cameras from all over the world. We used geographic coordinates to show markers of the camera's locations on the map. After an user clicks a marker in desired location a popup appears showing more details. User can click on the camera image to see a live view from this particular camera in a new window.
<img src="src/assets/Screenshot.png" width="900">

## Challenges and Wins
Webcamstravel allows to access just fifty cameras at the same time. We decided at the first render to show 50 most popular cameras in the world. Then fifty most popular in the 200km radius from the place where a user clicks.

___
 ## Future Improvements
 - Replace the external Indeed website job search link with an API
