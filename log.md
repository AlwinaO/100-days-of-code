# 100 Days Of Code - Log

### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)

### Day 1: January 7, 2019 
**Today's Progress**: Sinatra Final Project - Used tux to check seeded data, build (and mount) `UsersController` and build login view.

**Thoughts**: I'm still learning how to use tux as it's helpful to make sure I seeded the database correctly but more importantly that the tables are set up properly when I add additional data and the models have the right associations. I also started building the users controller and set up RESTful routing for the login and signup routes, as well as, build the login view. I checked everthing in the browser to make sure the routes are hitting the next in the controller. This mostly makes sense but sometimes I get confused with which verb/action to write. Work in progress...

**Link(s) to work**: [Conferences App](https://github.com/AlwinaO/conferences)

### Day 2: January 8, 2019

**Today's Progress**: Sinatra Final Project - Added `sysrandom` gem for session secret to Gemfile, enabled sessions/set session_secret in ApplicationController and build control flow in `get '/login'` route to find, authenticate and log in user.

**Thoughts:** I'm following a video from one of the Sinatra Section Tech Leads to build my app and reinforce my understanding of building a Sinatra application. It's helpful because I participated in the study group for the Sinatra Live Build and now I can follow along as I build my own app. I also reviewed `:session_secret` and added the `sysrandom` gem to my application instead of adding some arbitrary `:session_secret`. Previewing the work I've done by adding `binding.pry` or going into `tux` also helps with understanding my project. When I logged in as a user with valid data and hit `pry` before I enabled :sessions, I got an empty `{}`. After I enabled :sessions, I got a hash with the `session_id csrf tracking` information. Checking my work as I go along is really helpful to understand how to build my application.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)
