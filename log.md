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

### Day 6: January 12, 2019

**Today's Progress**: Sinatra Final Project - Add `ConferencesController` and mount in `config.ru`. Add link to create a new entry to `layout.erb`. Create new and show pages. Add routes in `ConferencesController` for `get /conferences/new`, `post /conferences`, as well as show and index routes. Build logic in `post /conferences` route for redirecting to welcome page if the user is not logged in and to make sure a user entered all the required fields.  

**Thoughts:** Definitely struggled with the logic for creating a new conference. For some reason, when I create a new conference it goes back to the welcome page. But when I `raise params.inspect`, I can see the params I entered. To be continued...

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 7: January 13, 2019

**Today's Progress**: Sinatra Final Project - Update `ConferencesController`. Update `index` and `show` pages to show all conferences or one conference, respectively. Update `post /conferences` to make sure a new entry is created, add code to find one conference in the `show` route and add code to find all conferences in the `index` route. Commented out the logic in `post /conferences` route for redirecting to welcome page because the new entry was not created although the user was logged in.  

**Thoughts:** Still working on the logic for creating a new conference if a user is logged in. For some reason, when I create a new conference it goes back to the welcome page. So I commented out that logic and will create a new method to help with this validation. Without this validation, I'm able to create a new entry and persist to the database.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 8: January 15, 2019

**Today's Progress**: Sinatra Final Project - In the `ConferencesController` action, I added back the logic in `post /conferences` route for redirecting to welcome page because the new entry was not created although the user was logged in.  Not able to validate user login to create a new entry.

**Thoughts:** Still working on the logic for creating a new conference if a user is logged in. For some reason, when I create a new conference it goes back to the welcome page. When I uncomment that logic I have the same problem. To be continued...

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 9: January 16, 2019

**Today's Progress**: Sinatra Final Project - No active coding today as I focused on learning more about User Authentication to change the user login logic.

**Thoughts:** I found a few resources to help with understanding user authentication. It's starting to make sense and I need to process it before I add any more code. I'm not sure if I should add code and see what works or what. To be continued...

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 10: January 17, 2019

**Today's Progress**: Sinatra Final Project - I fixed my user login by adding `ENV ['SESSION_SECRET']` to my `config/environment.rb` file. 

**Thoughts:** When I set the `session_secret` to the `ApplicationController`, added the `sysrandom` gem to the `Gemfile` and `bundle install`, I forgot to also add `ENV ['SESSION_SECRET']` to my `config/environment.rb` file. So every time I logged in a user who create a new entry, the app could not set session to the `current_user`. These were extra steps I added to my app to make the session secure but I didn't have all the pieces in play. Now I know.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 11: January 18, 2019

**Today's Progress**: Sinatra Final Project - Add links to edit/delete a conference. Add an edit form to edit a conference. Add and test edit/delete routes in controller. Build in logic to validate the current_user can edit a conference that the user created. 

**Thoughts:** Every time I add a feature, link, etc., I should test it to make sure it works and/or goes where it should go. When things don't work, I can easily figure out where I went wrong when I'm missing a step.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 12: January 19, 2019

**Today's Progress**: watched a workshop on test driven development in ruby and Rails with @RubyGuides. 

Sinatra Final Project - update link to delete a conference. Add delete link to edit page. Build and test delete route in controller. Add p tags to conference name.

**Thoughts:** Every time I add a feature, link, etc., I should test it to make sure it works and/or goes where it should go. When things don't work, I can easily figure out where I went wrong when I'm missing a step.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 13: January 20, 2019

**Today's Progress**: Sinatra Final Project - protect edit/delete links with `authorized_to_edit?` helper method and add same to show view, figure out how to format the date of a conf (work in progress). Show nav bar if user is logged in, update redirect after deleting a conference. 

**Thoughts:** More work on user_input validations and making sure unauthorized users are not changing conferences.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 14: January 22, 2019

**Today's Progress**: Sinatra Final Project - Add sinatrat-flash gem and register in `ApplicationController`. Add flash messages to different routes and flash logic to `layout.erb`. Update routes with validation for empty strings and validate user login. Add `back` link to login and sign up pages so the user can go to the right page to login or sign up. Update description/license in readme. Update spec with completed tasks.

**Thoughts:** Flash messages are added to controller actions that end in redirect. If they are added to render pages, then they will always show; flash messages are intended to last for one HTTP request. Also, when I added the gem `sinatra-flash`, I did not have to require the gem in my `ApplicationController` because it was loaded in `config/environment.rb`, which requires all gems through `bundler/setup`. (add link to sinatra-flash documentation and image of my code) 

`require` will require any files I've added to my project, while `require_relative` requires a path to a file.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 15: January 23, 2019

**Today's Progress**: Sinatra Final Project - Add `flash[:errors]` to UsersControllers and layout.erb. Add a user's list of conferences the user added.

**Thoughts:**  I need to re-work the code to add the user's conference list. 


**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 17: January 26, 2019

**Today's Progress**: Sinatra Final Project - update `flash[:errors]` and `flash[:messages]` to `UsersControllers` `users/login` action. Update the user model with ActiveRecord validations (`validates :name, :email, presence: true`  `validates :email, uniqueness: true`). The user's conference list works on the user's show page works. I also added a helper method to `redirect_if_not_logged_in`. Added additional `flash[:errors]` and `flash[:messages]` to the `ConferencesControllers`.

**Thoughts:**  When I add updates to my code, I should re-run the server so I can see those changes reflected. I had updated the user's show page to include a list of the conferences they added and it was loading. Now when I login the user, the conference list is populated. I need to re-work the code in `layout.erb` to add the link to the user's conference list on the user's show page. I also need to work on formatting the date. I have to update my ruby version to 2.5.0 in order to install the `date` gem. I'll try to globally update the ruby version on my computer versus just my project's ruby version.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 18: January 27, 2019

**Today's Progress**: Sinatra Final Project - completed my project. Did a work around for the date by changing the date to a string in my seed file. Now the user can add the date with slashes or dashes.

**Thoughts:**  Glad to be done with this project. Will update log with link to blog post for full details.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 19: January 28, 2019

**Today's Progress**: Sinatra Final Project - Include updates from recent commits.

**Thoughts:**  Glad to be done with this project. Will update log with link to blog post for full details.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)

### Day 20: January 29, 2019

**Today's Progress**: Used Pramp for coding interview for the first time.

**Thoughts:**  I need to practice coding with algorithms!

**Link to work:** www.pramp.com

### Day 21: January 30, 2019

**Today's Progress**: Sinatra Final Project - fix dates in seed file; remove duplicate Welcom, user! line in user's show page. Committed final changes to repo.  Record video walkthrough, explaining how the app works and some challenges I encountered. Added blog outline to Wordpress site.

**Thoughts:**  Excited final project is just about done and looking forward to assessment.

**Link to work:** [Conferences App](https://github.com/AlwinaO/conferences)











