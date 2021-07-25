![Cover Image](./assets/cover.png)

# Using Remote API Data in an Alexa Skill Response

This is an Alexa skill template that shows how to use results from a remote API in an Alexa response. Using data from an external API is common in Alexa skills. But if you're new to building skills, or new to Node.js/JavaScript, using data from an external API can seem tricky. Hopefully the example code in this template helps simplify things.


### Live example
There is a live example of this skill that you can try from your Alexa device. Just enable the [Ground Control Alexa skill](https://www.amazon.com/Dabble-Lab-Ground-Control/dp/B075CWGY1P/ref=sr_1_sc_1?ie=UTF8&qid=1514557483&sr=8-1-spell&keywords=grond+control+alexa+skill). You can do that by saying: `Alexa, enable Ground Control` and then `Alexa, open Ground Control`.

The skill returns a list of astronauts currently in space. It gets the data from [api.open-notify.org](http://api.open-notify.org/astros.json). However, the code is written so you can easily change it to call a different API.

### Using this skill template

1. If you don't have one already, create an [Amazon Developer account](https://developer.amazon.com/).

2. Click the button below to deploy the code for this skill into your Alexa developer account. 

    [![Custom badge](https://img.shields.io/endpoint?url=https://badges-shields-io-88j4y07yzimq.runkit.sh)](https://deploy.dabble.dev/deploy/v2/hegv314gqw)

3. In the Alexa developer console, set the skill's invocation name.

4. Test the skill with your device or the Alexa simulator.

5. Modify the skill code to call a different API.

### About the code

There are a ton of ways to call an API using NodeJS. In this skill, the `getRemoteData` function in the [index.js](./lambda/custom/index.js) uses the native [http module](https://nodejs.org/api/http.html) or the native [https module](https://nodejs.org/api/https.html) to make an [HTTP GET](https://www.w3schools.com/tags/ref_httpmethods.asp) request to a provided URL. 

There are other node modules that could be used to call an API, like the popular [axios](https://github.com/axios/axios) module. The http/https modules were used here because they are native to NodeJS. However, the axios module can be a lot easier to work with - especially for more complex cases - for example, when you need to get results from multiple endpoints before returning a response.