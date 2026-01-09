# Trying shinylive


## Github deployment of a single app.R file

The process is:  
 
``` r
usethis::use_github_action(url="https://github.com/posit-dev/r-shinylive/blob/actions-v1/examples/deploy-app.yaml")
```

Make sure to allow github Pages deployment from a Github Actions.

It works at <https://rfrelat.github.io/test-shinylive/>

## Page deployment with a single app

The process is
``` r
shinylive::export("myapp", "site")
httpuv::runStaticServer("docs")
```

Make sure to allow github Pages deployment from a branches and the /docs folder.
It works well and the Shiny app can be found at <https://rfrelat.github.io/test-shinylive/>

## Page deployment with two apps

The process is

``` r
# export app1
shinylive::export("app1", "docs", subdir = "app1")
# export app2
shinylive::export("app2", "docs", subdir = "app2")

# then check them out:
httpuv::runStaticServer("docs/")
# then add
# http://127.0.0.1:7446/app1/
# http://127.0.0.1:7446/app2/
```

It works well and the two Shiny apps can be found at :  
<https://rfrelat.github.io/test-shinylive/app1/>  
<https://rfrelat.github.io/test-shinylive/app2/>  