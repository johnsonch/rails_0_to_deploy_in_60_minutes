#Presenter notes:
* Cloud 9 overview
* Setup git config
  ```
    $ git config --global user.name 'Chris Johnson'
    $ git config --global user.email 'chris@johnsonch.com'
  ```

* Cloud 9 generates a rails project for you we're going to remove that

	```
    $ rm -rf *
	```
* Then install rails 5

    ```
    $ gem install rails
    $ rails -v
    $ rails new crux
    $ cd crux
    $ bundle install
    $ bundle exec rails s -b $IP -p $PORT #this is only for cloud9
    ```

* Explore project structure
  * MVC, Configuration, Gemfile, Asset Pipeline
* Git

	```
	$ git init .
	```
* explore the ```.gitignore``` file

* Static pages controller
```$ bundle exec rails generate controller static_pages index about````

* Add routes
  ```ruby
  get '/about' => 'static_pages#about'
  root 'static_pages#index'
  ```

* Add some styling
	* [http://bootswatch.com/simplex/](http://bootswatch.com/simplex/)
	* Create app/assets/stylesheets/simplex.css and add contents from bootswatch template

  * Add design html to our layout, add the following code to application.html.erb

```
<nav class="navbar navbar-default">
<div class="container-fluid">
    <div class="navbar-header">
    <a class="navbar-brand" href="#">Crux</a>
    </div>
    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-2">
    <ul class="nav navbar-nav">
        <li class="active"><a href="#">Make Me Link to Paste</a></li>
        <li><a href="http://tiffzhang.com/startup/index.html?s=454565081279">About Youscribble</a></li>
    </ul>
</div>
</nav>
<div class="container">
    <%= yield %>
</div>
<footer>
    <p>&copy; Youscribble</p>
</footer>
```

	* Add some fun to our home page

```
<div class="row">
  <div class="jumbotron">
    <h1>Crux</h1>
    <p>Paste your stuffs</p>
    <p><a class="btn btn-primary btn-lg">Learn more</a></p>
  </div>
</div>

```

* Let's add our first real feature
```
$ bundle exec rails generate scaffold Paste title:string code:text slug:string
```

* Write the changes to the database
```
$ bundle exec rake db:migrate
```

^ NOTE: What's up with all this bundle exec stuff?  Why do I have to type more?

* Ok so this is fine, but not a real workflow. Let's make the following changes:
	* When someone goes to /pastes we show them the form to create a paste

	```
	def index
      @paste = Paste.new
      render :new
  	end
	```

	* Style our form to be more like the wireframe

```
<div class="row">
<div class="col-lg-12">
<% if @paste.errors.any? %>
    <div id="error_explanation">
    <h2><%= pluralize(@paste.errors.count, "error") %> prohibited this paste from being saved:</h2>
    <ul>
    <% @paste.errors.full_messages.each do |message| %>
        <li><%= message %></li>
    <% end %>
    </ul>
    </div>
<% end %>
</div>
</div>
<div class="row">
<%= form_for(@paste, :html => {class: "form-horizontal"}) do |f| %>
<fieldset>
    <legend>New Crux</legend>
<div class="form-group">
    <%= f.label :title, class: "col-lg-2 control-label" %><br>
    <div class="col-lg-10">
    <%= f.text_field :title, class: "form-control" %>
    </div>
</div>
<div class="form-group">
    <%= f.label :code, class: "col-lg-2 control-label" %><br>
    <div class="col-lg-10">
    <%= f.text_area :code, class: "form-control", rows: 22 %>
    </div>
</div>
<div class="form-group">
    <%= f.label :slug, class: "col-lg-2 control-label" %><br>
    <div class="col-lg-10">
    <%= f.text_field :slug, class: "form-control" %>
    </div>
</div>
<div class="form-group">
    <%= f.submit %>
</div>
</fieldset>
<% end %>
</div>
```
	* Have our paste show page use ```<pre>``` tags around the code

```
<p id="notice">
  <%= notice %>
</p>
<p>
  <h2><%= @paste.title %></h2>
</p>
<p>
  <pre>
  <%= @paste.code %>
  </pre>
</p>
```

* Next we can make oure pastes have nice urls by using a slug.

  * Model
```
class Paste < ApplicationRecord
  before_create :generate_slug


private
  def generate_slug
  self.slug = SecureRandom.urlsafe_base64
  end
end
```


	* Generate a slug for the user and show the page at that URL
		* Controller

```
# update redirect on create
paste_path(id: @paste.slug)

# update callback
@paste = Paste.find_by(slug: params[:id])
```


	* View - remove slug field
	* Update layout to have links correct to pastes_path
```
<li class="active"><%= link_to "New Paste", pastes_path  %></li>
```




* Mini test?

```
test "generates slug after create" do
  @paste = Paste.create(title: 'foo.bar', code: 'def new do')
  assert @paste.slug != nil
end
```
