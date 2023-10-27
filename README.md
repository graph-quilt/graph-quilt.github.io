# graph-quilt.github.io

## Setup

Following installation guide [here](https://jekyllrb.com/docs/).  

## Test Locally

```
$ cd docs
$ bundle exec jekyll serve
```

## Ruby version 3.2.X Notes

If you see the error `Liquid Exception: undefined method untaint' for "Welcome to Jekyll!":String in /_layouts/post.html jekyll 3.9.2 | Error: undefined method untaint' for "Welcome to Jekyll!":String`, 
you might need to update gem github-pages to make use of liquid-4.0.4 which is already in Gemfile.  Run the ff and test again.

```
$ bundle update github-pages
``` 