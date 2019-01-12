# 100 Days Of Code - Log

### Day 1: January 7, 2019 
**Today's Progress**: Sinatra Final Project - Used tux to check seeded data, build (and mount) `UsersController` and build login view.

**Thoughts**: I'm still learning how to use tux as it's helpful to make sure I seeded the database correctly but more importantly that the tables are set up properly when I add additional data and the models have the right associations. I also started building the users controller and set up RESTful routing for the login and signup routes, as well as, build the login view. I checked everthing in the browser to make sure the routes are hitting the next in the controller. This mostly makes sense but sometimes I get confused with which verb/action to write. Work in progress...

**Link(s) to work**: [Conferences App](https://github.com/AlwinaO/conferences)

### Day 2: January 8, 2019

**Today's Progress**: Sinatra Final Project - Added `sysrandom` gem for session secret to Gemfile, enabled sessions/set session_secret in ApplicationController and build control flow in `get '/login'` route to find, authenticate and log in user.

**Thoughts:** I'm following a video from one of the Sinatra Section Tech Leads to build my app and reinforce my understanding of building a Sinatra application. It's helpful because I participated in the study group for the Sinatra Live Build and now I can follow along as I build my own app. I also reviewed `:session_secret` and added the `sysrandom` gem to my application instead of adding some arbitrary `:session_secret`. Previewing the work I've done by adding `binding.pry` or going into `tux` also helps with understanding my project. When I logged in as a user with valid data and hit `pry` before I enabled :sessions, I got an empty `{}`. After I enabled :sessions, I got a hash with the `session_id csrf tracking` information. Checking my work as I go along is really helpful to understand how to build my application.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 3: January 9, 2019

**Today's Progress**: Sinatra Final Project - Built Helper methods `logged_in?` and `current_user`; complete the signup page and set up the user's show page.

**Thoughts:** Memoization - to limit the number of database calls; if the value is stored in `@current_user` then we don't have to query the database to find the user. Separation of concerns for each route; each route should only do one thing. Render from a `get` request. Redirect from a `post`, `patch`, `delete` request. Need the url to match the contents of the page.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 4: January 10, 2019

**Today's Progress**: Sinatra Final Project - Complete `login`, `signup` and `show` routes; add `logout` route; update the user's show page and test in `tux`.

**Thoughts:** I see the need use `tux` to make sure anything I add to the database is persisted; I have to remember to I use `new` to `save` and if I use `create` I don't need to further persist the data. The video I'm following is helpful because I can see now where I made mistakes with my routes. Where I can use `raise params.inspect` to check `params` in the browser. Also, use `binding.pry` to check the contents of `params` and database entries. Repitition is key.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 5: January 11, 2019

**Today's Progress**: Sinatra Final Project - Add links to the welcome page so the user can login or signup. Add navigation links to the layout page so the user can logout or view all the conferences. Add logic to the index route in the application controller to check if the current user is logged in. 

**Thoughts:** Simple work today. Just checking that links work and adding functionality to the web app.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)
