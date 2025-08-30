# Overall Infrastructure Architecture

Our infrastructure is hosted on Digital Ocean as much as possible, with some exceptions.

## Digital Ocean Services

- **App Platform**: Both the frontend and backend codebases are deployed using digital ocean app platform. This is a serverless infrastructure solution that 
  takes a containerized application/codebase in a popular framework and manages hosting it.
- **Postgres Database**: The API has a postgres dependency. We use a managed digital ocean postgres database for this.
- **Firewalls**: These are all configured through the default digital ocean settings.
- **DNS**: These are configured through digital ocean networking settings.
- **Image registry**: The API can only be deployed via a custom image - app platform has no out of the box integrations for rust apps - so we use a 
  digital ocean image registry for this.

## Elestio Hostname

The `sudandigitalarchive.com` hostname is purchased from [elestio](https://elest.io/) as hangover of trialing use of 
[bayanat](https://syriaaccountability.org/bayanat-sjacs-new-open-source-database/) for the archive.

Note that the CNAME and other records are not managed here - these are done from within digital ocean.

## Environments

Note that we currently _only_ have a production environment. There is no dev/staging environment in order to keep costs down. 
There are instructions in each of the repos on how to do development on your local machine, which is probably going to be the way forward for a while unless
we get much money.