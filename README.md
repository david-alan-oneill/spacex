# spacex

1) Have you worked with APIs before? If so, please provide brief details of relevant projects.

Yes, the current project I am working on uses the API Platform Framework. We use this for everything from JWT user token generation to our restful backend for multiple in house applications.   

2) How will you approach this task?

Firstly I will make myself familiar with the spacex API. I will use postman to test making requests and become comfortable with the response and data types. My aim will then be to build a month style view, this will open by default on the current month, there will be "previous" and "next" type buttons so the user can navigate between them. If there was/is a launch on a day I will highlight the date and give some high level information. I would like the ability to click on a highlighted date and display more in depth information in a modal. The two main components I envisage at this time are Month.Vue and Date.vue, they will be reusable so should cover the bulk of what is needed.

3) Given more time what would you improve?
I think using a vuex store would be better here, I would be able to fetch the data in one call and then have functions that could filter the data down into months and days when needed. I would also set up some models so that I can pass objects as types as apposed to just generic objects.
