## Trying shinylive


## Github deployment of a single app.R file

The process is:  
 
``` r
usethis::use_github_action(url="https://github.com/posit-dev/r-shinylive/blob/actions-v1/examples/deploy-app.yaml")
```

Make sure to allow github Pages deployment from a Github Actions.

It works at <https://rfrelat.github.io/test-shinylive/>

## Page deployment of a single app

So far, the process is
``` r
shinylive::export("myapp", "site")
httpuv::runStaticServer("docs")
```

Make sure to allow github Pages deployment from a branches and the /docs folder.