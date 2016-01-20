#Middleman 4 Boilerplate
Oh It's so f**king nice.

####Deploy

Create an app (Run Once)
```
heroku create <<MYAPP>>
```

Initial Setup (Run Once)
```
$ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

Deploying (Every deploy)
```
git push heroku master
```
