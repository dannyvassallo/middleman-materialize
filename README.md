#Middleman 4 Boilerplate

Oh It's so fucking nice.

####Deploy

Initial Setup
```
$ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
...
$ cat .buildpacks
https://github.com/heroku/heroku-buildpack-ruby.git
https://github.com/hashicorp/heroku-buildpack-middleman.git
```

Deploying
```
heroku create <<MYAPP>>
git push heroku master
```
