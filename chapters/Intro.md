Why WebPages?
=====

- [x] **automatic routers**. We DON'T have `urls.py` url mapping *(like we do in Django)*. Instead the web framework search controllers and actions based on convention `controller_name/action_name/...` *(`/blog/view/123/` call `view` action of `Blog` controller with `123` argument)*. To disable controller or model - rename it with leading underscore, like this `controllers/_blog.py`
- [x] **check broken urls**. We can run command `check urls` to detect broken urls and fix them manually. You don't need to support url mapping to do this extra job
- [x] **MVC**. We DON't need to use reusable applications *(like in Django)*. We have root folders `models`, `templates` (views) and `pages` (controllers) where you place all your code. You don't need to think about *"In what app I should place this new model?"*. Have an idea? - Code it!
- [x] **settings inheritance**. Project has own settings file and can redefine default settings for models and controllers. Settings file contains grouped configuraions per component *(NO global names like in Django)*
- [x] **generate project from command-line**. And each model/view/controller also sould be. To add new model - we use command-line to create appropriate model, view and controller with appropriate actions and templates for this new model (like in **Ruby on Rails**)
- [x] **easy migrations**. When we rename field or add new one - we do it in command-line and it save our changes to migration file
- [x] **data validation**. All data come to database only via forms (like in **Django**, but forms are part of Model). In total - the Model can return us the From that we requested *(`User.get_registration_from()` or `User.get_edit_profile_form()`)*
- [x] **middleware support**. Tou can add own middleware classes to do something before and after execution of each Controller's action
- [x] **login user out of the box**. To save your time we ship each new project with registration and login pages. You can login with any social network as well. Configurable in `settings.yaml`
- [x] **[ORM](https://github.com/webpages/orm)**. For the first time we can use third-party ORM's *(Django ORM or SQLAlchemy). But we wish to create simplified syntax like this `User.first` or `User.all.filter((F.name='Tony' and F.age.in(10, 20, 30)) or F.roles.name='admins')`
 **template engine** with python-like syntax, without closing tags *(styled with indentation, like in `Slim` for Ruby)*
