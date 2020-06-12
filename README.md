# Build a Rails App

## Overview

In this lesson you're going to build a complete Ruby on Rails application that manages related data through complex forms and RESTful routes. The goal of the application is to build a Content Management System, whether the content being managed is Blog Posts, Recipes, a Library of Resources, or any domain model that lends itself to these requirements (the majority of ideas you could come up with would probably meet the requirements).

## Requirements

1. Use the Ruby on Rails framework.

2. Your models must include a `has_many`, a `belongs_to`, and at least two `has_many :through` relationships. You may include more models to fill out your domain, but there must be at least one model acting as a join for one of the has_many through relationships. Also, make sure that every table has at least two simple attributes outside its timestamps and foriegn keys. For example, a `Ticket` model may contain `seat` and `departure_time` attributes.

3. Your models should include reasonable validations for its simple attributes. You don't need to add every possible validation, but the models should defend against invalid data.

4. You must include at least one class level ActiveRecord scope methods. Scopes have not been covered in a lesson or lab, but they are conceptually and syntactically simple. [Read the Rails documentation to discover how to write a scope](https://guides.rubyonrails.org/active_record_querying.html#scopes). To some extent these class scopes can be added to power a specific individual feature, such as "My Overdue Tasks" in a TODO application, scoping all tasks for the user by a datetime scope for overdue items, `@user.tasks.overdue`.

5. Your application must provide a standard user authentication, including signup, login, logout, and passwords. You can use [Devise](https://github.com/plataformatec/devise) but given the complexity of that system, you should also feel free to roll your own authentication logic.

6. You must make use of a nested resource with the appropriate RESTful URLs. Additionally, your nested resource must provide a form that relates to the parent resource. Imagine an application with user profiles. You might represent a person's profile via the RESTful URL of `/profiles/1`, where 1 is the primary key of the profile. If the person wanted to add pictures to their profile, you could represent that as a nested resource of `/profiles/1/pictures`, listing all pictures belonging to profile 1. The route `/profiles/1/pictures/new` would allow one to upload a new picture to profile 1.

7. Your forms should correctly display validation errors. Your fields should be enclosed within a fields_with_errors class and error messages describing the validation failures must be present within the view.

8. Your application should contain Unit tests for all of your models and at least Integration test. Your Integration test can be a controller test, a request test, a feature test, or a system test. Start by adding `rspec-rails` to your `Gemfile` and initializing it. Before you start, reach out to a TA or instructor about getting some guidance for appropriate tests you may add. Use [Relish documentation](https://relishapp.com/rspec/rspec-rails/v/4-0/docs/) to learn more about these different types of tests in `rspec` and how to set them up.

9. Your application must be, within reason, a DRY (Don't-Repeat-Yourself) Rails app. Logic present in your controllers should be encapsulated as methods in your models. Your views should use helper methods and partials to be as logic-less as possible. Follow patterns in the [Rails Style Guide](https://github.com/bbatsov/rails-style-guide) and the [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide).

10. Your application should conform to Nitro's Ruby linting conventions. The `.rubocop.yml` included in this repo should be copied over to your application. Running `rubocop` from your application's root should return a `no offenses detected` message. (Don't forget to add "rubocop" to your Gemfile.)

11. Your app should include a `README.md` with a description of the project and an installation guide (e.g. fork and clone repo, migrate db, bundle install, etc).

12. **Do may not** use scaffolding to build your project. Your goal here is to learn. Scaffold is a way to get up and running quickly, but learning a lot is not one of the benefits of scaffolding. That's why we do not allow the use of scaffolding for projects.

### Example Domains

- A Recipe Manager - Should provide the ability to browse recipes by different filters such as date created, ingredient count, rating, comments, whatever your domain provides. Additionally ingredients would need to be unique so that the first user that adds Chicken to their recipe would create the canonical (or atomic/unique/individual) instance of Chicken (the only row to ever have the name Chicken in the ingredients table). This will force a join model between ingredients and recipes and provide an easy way to group recipes by ingredients, which would be a great view to implement. Associating some user-centric data regarding recipes such as ratings or comments would further fill out the domain and provide some great learning experiences.
- A Group Task Manager - An application that allowed the creation of task lists with individual tasks that can be assigned to a user would flex the majority of the requirements of this assessment. You would be able to create a list of tasks, add tasks to that list, and assign those tasks to a user.

### Restricted Domains

- A Blog App - We used a Blog domain design for a lot of the rails lessons and code-alongs.
- An Amusement Park - This is the domain design for one of the final Rails projects. Try to find inspiration from this project and build something unique and different.

## Instructions

1. Create a new repository on GitHub for your Rails application.
1. Build your application. Make sure to commit early and commit often. Commit messages should be meaningful (clearly describe what you're doing in the commit) and accurate (there should be nothing in the commit that doesn't match the description in the commit message). Good rule of thumb is to commit every 3-7 mins of actual coding time. Most of your commits should have under 15 lines of code and a 2 line commit is perfectly acceptable. **This is important and you'll be graded on this**.
1. Add the requirements.md from this repo to your project. Then check each box (replace the space between the square braces with an x) and write below each line with how you've met the requirement.

### Be Prepared to:

1. Give a minimal description of application, then have the reveiwer walk through the application. 5 minutes.
1. Run down each item in your `requirements.md` and explain how you've met each criteria. 5-10 minutes
1. Refactor code and/or extend the application with a new feature, more data, etc. 45-50 minutes.
1. Submit an improved version.
