# Heroku installation

clone this project

install [heroku cli](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)

and login with `heroku login`

In the project folder

Install dependencies

`bundle install`

Create a new project

`heroku create`

Add a postgress database

`heroku addons:create heroku-postgresql:hobby-dev`

> Created postgresql-horizontal-49879 as DATABASE_URL


generate the tripkey

> rake gentripkey[512]

save it on heroku

`cat config/trip.key | base64`

copy the output and save on heroku

`heroku config:set TRIP_KEY="kin+PHFyU9lDi6bKwvy+vUtHgDvrYi0QPx8kfGZ9Vdu3uY3GC55hd7Gsc2LsWkAz5/FCNTICUtN8SiWnKrF5vZP/sg4njwdOZR0pIeHTTvXaBWx2bGuUKd7SIhJrXOqJx8G/eyecsXFu6FFKxUq3ChMtUO8WqAt4mjLVdep3MTTTqwu+7HmYzkWFsVTtcHaMtlcwaTqDhfxEMF6+OfVNsdddchuNr5c1uy9yD0pt5GPizcSdNOB6aGkQcPcjISo0/7nQs8zMPhAIW8XZhYcvA4gxjiE/VTaAup7Cp5F4FuIH4tfsdffcgzTdsZLGDjrR8CP9tQ1hPFKYetfZBcqof/Xv4BLxC+RvPPQID+2x9l4n6muhaGS3Ow8C848ooYO7o0Tvts9KZ6j8lKK3rBVlCbxXiDpSWXLqBnYr7XfidryVYT8Apt52yWXpYnORXMVCuNl8CNRFqzNKESQByEHgJSHFg4pjMaS9Pum7pm6YyugBQzhCow8FD8WlG/ILXWz1NHN7Z0dAg5t4C7zVZhTJYhenhyH1tR5/Ydoj3eq98d27fS/r5iydzQM7G4vQ1UDtJL4loSNcnK7FNty84WlvdaT7WGNsFPb4luMy/e62DQxrMyjDZUvEN+M2FmXnmtAQ6xnao4qaEH7jHRhnCG8/w98zIuZrLNSgLJiqp1R5N+4="`


deploy

`git push heroku HEAD:master`

migrate

`heroku run rake db:migrate`

Create the admin user

`heroku run rake db:init`

> Running rake db:init on ⬢ quiet-earth-26290... up, run.8879 (Free)
> Added admin account (username: admin / password: admin)
