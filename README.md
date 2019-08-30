[![Heroku](https://heroku-badge-gae.herokuapp.com/?app=digital-nomad-hub)](https://digital-nomad-hub.herokuapp.com/)

# SEI Project 2 - Digital Nomad Hub

Retrieves a map of locations of potential destination for digitals nomads using live streaming webcams.

**<a href="https://digital-nomad-hub.herokuapp.com/" target="_blank">Visit the Website</a>**

![General Assembly Logo](./screenshots/ga-logo.png)

### Timeframe
> 48h

### Team
- Gaetano Barreca: https://github.com/gaebar
- Kasia Wypychewicz: https://github.com/kasiaaguti

### Brief
Build a React application that consumes a public API.
Have several components - At least one classical and one functional.
The app should include a router - with several "pages".
Have semantically clean HTML.
Be deployed online and accessible to the public.
Work in pairs.
​
### Tech Stack
* React
* Axios
* Insomnia
* Webpack
* HTML5
* CSS
* Bulma
* Teletype
* Heroku

### APIs
* Mapbox
* Rapid webcams

___

## Website Summary
Digital Nomad Hub was the second project during the General Assembly Software Engineering Immersive course (Week 5). The project was made in collaboration with Katarzyna.

We had to render an app that retrieves data from a public API in an interesting and engaging manner. We had just under 48 hours to achieve this goal, making it extremely time-sensitive. We chose to create a web app called Digital Nomad Hub, which allows users to retrieve a map of locations of potential destination for digitals nomads, using the Mapbox and Rapid webcams APIs.

My part in the project included creating a Mapbox API integration, display the results on the map and general styling of the map.

___
### Approach
As this was a pair coded hackathon with a very limited timeframe, we chose was to focus on functionality. For styling we used Bulma which was very helpful. Most of our coding was done on one laptop, so we discussed each piece of code and the best approaches. We also used the Teletype team coding tool.

### Process
The core idea was to used Webcamstravel API https://webcamstravel.p.rapidapi.com/ and render it on a map (for which we used Mapbox). Webcam API gave us access to public cameras from all over the world. We used geographic coordinates to show markers of the camera's locations on the map. After an user clicks a marker in desired location a popup appears showing more details. User can click on the camera image to see a live view from this particular camera in a new window.

## Visuals

### Home page
![Home page](./screenshots/home-page.png)

### First render of a map

![Map view](./screenshots/all.png)

### More cameras for a clicked location
![Zoomed in map](./screenshots/italy.png)

### Pop up on a clicked marker
![Popup images](./screenshots/pop-up.png)

### Rendering first set of markers

```javascript
this.markers.forEach(marker => marker.remove())
this.markers = this.props.markers.map(point => {
  // create custom popups one for each marker
  const el = document.createElement('div')
  el.className = 'marker'
  el.style.backgroundImage = 'url(' + point.image.current.preview + ')'
```

### Accessing a set of webcams after user clicks on particular location

```javascript
getWebcamList(lat, lng) {
  axios.get(`https://webcamstravel.p.rapidapi.com/webcams/list/nearby=${lat},${lng},250/limit=50?show=webcams:image,location,player`,
    { headers: {
      'X-RapidAPI-H': 'webcamstravel.p.rapidapi.com',
      'X-RapidAPI-Key': rapidApiKey
    }
    })
    .then(res => {
      this.setState({ points: res.data.result.webcams}, () => console.log(this.state.points))
    })
    .catch(err => console.log(err))
}
```

## Challenges and Wins
Webcamstravel allows to access just fifty cameras at the same time. We decided at the first render to show 50 most popular cameras in the world. Then fifty most popular in the 200km radius from the place where a user clicks.

### Key Learnings
The Digital Nomad Hub was my first pair programming experience. It was a great way for me to realize how wonderful is to work in a group and share time, knowledge and idea. Kasia and I found interesting building this specific app and explore how to use APIs and using a CSS library like Bulma.

 ### Future Improvements
 - We might work more on user experience regarding popups and redirecting to webcams
 - Replace the external Indeed website job search link with an API

---

## Installation

Install dependencies:

`yarn install`

### Run the app

Compile the application code:

`yarn buid`

Start the development server:

`yarn serve`

## Deployment

With heroku, automatically deploys when new code is pushed to `master`
