<!-- footer: @johnsonch :: Chris Johnson :: Ruby on Rails 0 to Deployed in 60 Minutes -->

#Ruby on Rails
##0 to Deployed in 60 Minutes
###Chris Johnson
![full](images/IMG_5283.jpg)

---
![full](images/that_conference_title_slide.png)

^ That conference title slide

---
![full](images/that_conference_sponsors.png)

^ That conference sponsors slide

---
#About me
![fit right](http://www.johnsonch.com/images/me.jpg)

* Chris Johnson
* Manager of Application Development at GettyImages
* Author at Pragmatic Bookshelf
* Part-Time Instructor at Madison College
* Owner at JohnsonCH, LLC
* @johnsonch => most places on the internet

---
#About my family
![fit right](images/family.jpg)

^ A picture of my famlily

* Husband
* Father of 2

---
#About GettyImages

> GettyImages is among the world’s leading creators and distributors of award-winning still imagery, video, music and multimedia products, as well as other forms of premium digital content, available through its trusted house of brands, including iStock© and Thinkstock©.

![inline](http://cyberpunklibrarian.com/wp-content/uploads/2014/03/getty_images_logo.jpg)

---
#Shameless Plug
![full](images/wbdev2_xlargebeta.jpg)

^ Cover of Web Development Recipes, second edition

---
![fit right](images/wbdev2_xlargebeta.jpg)

* http://bit.ly/web-development-recipes-2nd-edition
* @webdevrecipes
* http://webdevelopmentrecipes.com

---
#Roadmap
![full](images/IMG_6005.jpg)

^ Race cars on the track at Road America

* Definitions
* Setting up a Development Environment
* Building "Crux"
* Deploying
* ???
* Profit!

---
##This is not a talk on how to build "enterprisy" applications

![full](images/GettyImages-546183276.jpg)

^ [^1]

[^1]: filmfoto | 546183276

---
##This is a talk on how to get started and perform one itteration of a simple web application

![full](images/GettyImages-154769124.jpg)

^ [^2]

[^2]: Image Source | 154769124

---
#Definitions
* Cloud IDE
* Heroku
* Ruby
* Ruby Gems
* Rails
* Git
* Bundler

---
# Cloud IDE

![full](images/GettyImages-532029221.jpg)

A tool for developing an application with nothing but a web browser.


^ [^3]

[^3]: Colin Anderson | 532029221

---
# Heroku

* Heroku is a PaaS company owned by Salesforce.com
* We'll be using this to deploy our application.
* They have a free tier!

![fit right](https://dl.dropboxusercontent.com/s/podds8x14tzqqcf/2016-08-05%20at%208.22%20PM.png)

---
# Ruby

##is

> A dynamic, open source programming language with a focus on simplicity and productivity. It has an elegant syntax that is natural to read and easy to write.

![fit right](https://upload.wikimedia.org/wikipedia/commons/thumb/7/73/Ruby_logo.svg/200px-Ruby_logo.svg.png)

---
#Ruby Gems

Simply a package manager for the Ruby language.

---
# Rails

> Rails is a web-application framework that includes everything needed to create database-backed web applications according to the Model-View-Controller (MVC) pattern.

![fit right](https://upload.wikimedia.org/wikipedia/en/thumb/e/e9/Ruby_on_Rails.svg/300px-Ruby_on_Rails.svg.png)

---
# Git

* I'm hoping you have all heard of Git if not find @coridrew or @dahlbyk!
* They each have a Git session on Wednesday.

---
# Bundler

* > Bundler provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed.


* > Bundler is an exit from dependency hell, and ensures that the gems you need are present in development, staging, and production. Starting work on a project is as simple as bundle install.

^ For the most part it is a nice tool, like any tool without proper use it can
cause much pain and suffering.

---
#Setting up an Development Environment
* Setup local machine?

^ You are going to need: Ruby, Ruby Gems, Rails, Bundler, Git all on your local machine

---
#Setting up an Development Environment
* Create a VM?

^ A little more isolated but still the setup process is going to take some work

---
#Setting up an Development Environment
* Use <insert hot new provisioning> technology

^ Again isolated but a poo storm

---
#Setting up an Development Environment
* Cloud IDE
 * [https://c9.io/](https://c9.io/)

^ This requires not much effort

---
#Which one is for me?

![full](images/182656049.jpg)

^ [^5]

[^5]: Dave and Les Jacobs | Blend Images | 182656049

^ Notes: Really it all depends on your comfort with the different technologies
and how much time you want to spend getting things going.

---
#Let's build
##Crux

![full](images/532029343.jpg)

^ [^6]

[^6]: Mike Kemp | Blend Images | 532029343

---
#Let's build - Wireframe

![inline fit](https://dl.dropboxusercontent.com/s/i2tmld3lp0keo31/2015-04-24%20at%208.31%20PM.png)

---
#Let's build - Model/Database plan
![inline fit](https://dl.dropboxusercontent.com/s/ls8zmsd4zqsap5x/2015-04-24%20at%208.34%20PM.png)



---
#Let's build
##To the editor

![full](images/170961794.jpg)

^ [^7]

[^7]: Paul Bradbury | OJO Images | 170961794

---
#Deploying to
#Heroku

![full](images/GettyImages-181817359.jpg)

^ [^8]

[^8]: Andy Ryan | 181817359


^ Notes
```
  ##Create the app
  $ heroku create
  ##Adjust gemfile to use postgres
  gem 'sqlite3', group: :development, :test
  gem 'pg', group: :production
  ##Rebuild gemfile.lock
  $ bundle install --without production
  ## Commit and push the app
  $ git add .
  $ git commit -am "commiting to push to heroku"
  ## Deploy
  $ git push heroku master
  ## Migrate our database
  $ heroku run rails db:migrate
  ## Find out where our app is running
  $ heroku domains
```

---
#Profit!
##Actually do y'all have any questions?

---
#Thank you
![fit right](images/wbdev2_xlargebeta.jpg)

* http://bit.ly/web-development-recipes-2nd-edition
* @webdevrecipes
* http://webdevelopmentrecipes.com
* @johnsonch
* http://blog.johnsonch.com

---
![full](images/that_conference_end_slide.png)

^ That Conference end slide.
