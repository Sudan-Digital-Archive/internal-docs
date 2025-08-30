# CI/CD

The frontend and backend both use Github actions for CI/CD. 

## Frontend

This one is very managed - Digital Ocean app platform has a built in integration for react apps, so when a new commit is added to this repo
it automatically deploys a new version of the site.

## Backend

This one is different since app platform has no out of the box integration for Rust/Axum apps. Instead, the pipeline builds a new container image and uploads the new
image to the digital ocean registry.

This then triggers a new deployment of the API - i.e. deployment fires whenever the API image tag is bumped.