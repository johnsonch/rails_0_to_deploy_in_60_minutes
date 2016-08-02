footer: @johnsonch :: Chris Johnson :: Ruby on Rails 0 to Deployed in 60 Minutes

#Ruby on Rails
##0 to Deployed in 60 Minutes
###Chris Johnson
![full](images/IMG_5283.jpg)

^ Photo Credit: Me

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
#About GettyImages

> GettyImages is among the world’s leading creators and distributors of award-winning still imagery, video, music and multimedia products, as well as other forms of premium digital content, available through its trusted house of brands, including iStock© and Thinkstock©.

![inline](http://cyberpunklibrarian.com/wp-content/uploads/2014/03/getty_images_logo.jpg)

---
#Shameless Plug
![full](images/wbdev2_xlargebeta.jpg)

---
![fit right](images/wbdev2_xlargebeta.jpg)

* http://bit.ly/web-development-recipes-2nd-edition
* @webdevrecipes
* http://webdevelopmentrecipes.com

---
#Roadmap
![full](images/IMG_6005.jpg)

^ Photo Credit: Me

* Definitions
* Setting up a Development Environment
* Building "Crux"
* Deploying
* ???
* Profit!

---
#Disclaimer
##This is not a talk on how to build "enterprisy" applications

---
#Definitions
* Cloud IDE
* Heroku
* Ruby
* Rails
* Git
* Bundler

---
#Setting up an Development Environment
* Setup local machine?
* Create a VM
* Use <insert hot new provisioning> technology
* Cloud IDE
 * [https://c9.io/](https://c9.io/)

---
#Which one is for me?

![full](images/182656049.jpg)

^ Photo Credit: Dave and Les Jacobs | Blend Images | 182656049

---
#Let's build
##Crux

![full](images/532029343.jpg)

^ Photo Credit: Mike Kemp | Blend Images | 532029343

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

^ Photo Credit: Paul Bradbury | OJO Images | 170961794

---
#Deploying
#Heroku

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
