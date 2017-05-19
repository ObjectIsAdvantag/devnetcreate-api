# LiveAPI: show activities happening live

a REST API to show activities happening live

build with sails.js, data persisted in postGreSQL

testable at https://devnetcreate-api.herokuapp.com/, for [DevNet Create 2017](https://devnetcreate.io/2017/)


## API Resources

Public ressources to search for activities
- GET /api/v1/activities/next: upcoming activities (all activities who begin after now, ie, do not comprise activities that are in progress) 
- GET /api/v1/activities/current: activities in progress (begin date is passed, but end date has not happened yet)
- GET /api/v1/activities: all activities ordered by begin date ASC

Note that the project also contains an Administration API secured by a Bearer token that lets administrators Create and Delete activities.

### POSTMAN

- collection: https://www.getpostman.com/collections/2ff525bd91e54f3295cd
- documenter: https://documenter.getpostman.com/collection/view/30210-5ef8ed70-4fbe-3854-3b01-c966a612705e


## Architecture

The API is implemented on top of Sails.js, http://sailsjs.org/

An instance of the API is deployed on Heroku servers, and persists its data into PostgreSQL.
- https://devnetcreate-api.herokuapp.com/api/v1/activities


# Companions

## Cisco Spark bot

Launch Cisco Spark and invite devnetcreate@sparkbot.io to meet the bot.

The bot consumes the API to display current and upcoming activities in Cisco Spark rooms:
- bot source code: https://github.com/ObjectIsAdvantag/devnetcreate-bot 


## Installation

- Go to Heroku, create a new PostgreSQL DB with a free plan
- Create a local.js file from the provided template
- Run the project with the drop database option to install the first version of it
- Optionally customize the [Activity](/api/models/Activity.js) fields
- NODE_ENV=development node app.js
- Test the API locally at http://localhost:1337
- Deploy the API on Heroku, and customize the env variable to point to the production database


## Dataset

You can use the postman collection to fill in data manually,
or simply write a batch in python or nodeJS to inject a CSV file via the API.


# License

[MIT](LICENSE)

Feel free to use, reuse, extend, and contribute
