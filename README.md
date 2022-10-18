# THINGS IN HERE

## GEMS

```
gem 'haml'
gem 'bootstrap-sass'
gem 'devise'
gem 'simple_form'
```
- i didnt use bootstrap sass
- devise set for turbo, rails 7
- from: https://dev.to/efocoder/how-to-use-devise-with-turbo-in-rails-7-9n9
- haml for devise links

```
%ul.nav.navbar-nav.navbar-right
	- if user_signed_in?
		%ul.nav.navbar-nav.navbar-right
			%li= link_to "New Article", new_article_path
			%li= link_to "Account", edit_user_registration_path
			%li= button_to "Sign Out", destroy_user_session_path, method: :delete
	- else
		%ul.nav.navbar-nav.navbar-right
			%li= link_to "Sign Up", new_user_registration_path
			%li= link_to "Sign In", new_user_session_path		
```

## MODELS
- devise user: has many articles
- articles belongs to user and categories
- categories have many articles

## OTHER
- filter the articles by categories, throught the articles path

```
%ul.list-group
	%li= link_to "All Articles", root_path, class: "list-group-item"
	- Category.all.each do |category|
		%li= link_to category.name, articles_path(category: category.name), class: "list-group-item"
```
