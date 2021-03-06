
# Grid intensity polyfill

_A polyfill, to build awareness of carbon intensity into javascript programs - move your code through time and space for greener digital products._

## Usage

```js
const GridIntensity = require('gridintensity-polyfill')

// initialise
gridIntensity = GridIntensity()

const carbonIndex = await gridIntensity.getCarbonIndex()

if (carbonIndex == 'low')  {
  // Huzzah! Energy is cheap! The wind is blowing and the sun is out,
  // the cost of energy is low, and the grid is also greener
  // than normal. Do network and CPU intensive stuff

  loadrichImages()

  await Promise.all([
    doExpensiveOperation(), preLoadVideo()
  ])

} else {
  // Eep - our grid is relying on more fossil fuels than usual, so
  // let's defer work til later, and serve a lighter weight experience
  // by default
  loadLiteImages()

  // if we have web workers available, let give them a job to do when
  // grid intensity is lower, so when the user comes back they have the
  // richer experience
  queueJobforWorker([
    doExpensiveOperation
    fetchVideo
  ])
}
```

### Background

We know that the internet runs on electricity. That electricity comes from a mix of energy sources, including wind and solar, nuclear power, biomass, fossil gas, oil and coal and so on,

We call this the *fuel mix*, and this fuel mix can impact on the *carbon intensity* of your code.

### Move your code through time and space

Because the fuel mix will be different depending when and where you run your code, you can influence the carbon intensity of the code you write by moving it through time and space - either by making it run *when* the grid is greener, or making it run *where* it's greener, like a CDN running on green power.

This API is designed to make that easier. It pulls data from open data sources, about the predicted carbon intensity of energy on the grid where code is run, and presents an object you can query, so you can make an application or website serve a different experience to end users based on the carbon intensity.

### TODO

_This is very incomplete. Sorry about that. I hope this gives an idea of where you can help if you're interested._

- [ ] Add support for API providers beyond the UK national grid (Electricity Map would be WONDERFUL)
- [ ] Add a 24 hour forward looking check, so there's less need to hit a single API endpoint. This is how forward markets for energy work for reals anyway.
- [ ] Add geo support to either use geolocation features in a browser, or some kind of educated guesses serverside so we use the correct country for grid intensity
- [ ] Write post to explain the idea in more detail
- [ ] Flesh out issues, and guidelines for contribution.
- [ ] Figure out how to get this into the the green web browser extension, to demonstrate how carbon awareness should be part of browsers by default. `user-agents` of change!
- [ ] Publish to NPM, and generate the compiled regular js into lib
- [ ] For browsers, include check for the kind of connection on a webpage, using the polyfill currently listed in the package.json
