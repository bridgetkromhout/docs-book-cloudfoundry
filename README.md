# Cloud Foundry Documentation

This project publishes the Cloud Foundry documentation as a web application.

## What's in this Repo

This repo uses the [Bookbinder gem](http://github.com/pivotal-cf/docs-bookbinder) to generate the documentation as a web application.

The config.yml file contains the list of topic repositories.

The master_middleman folder contains the template used for publishing

This repository does not contain the documentation content. That's contained in the topic repositories listed in the config.yml.

## Topic Repositories

The topic repositories that make up the Cloud Foundry documentation set are:

* [Cloud Foundry Concepts](http://github.com/cloudfoundry/docs-cloudfoundry-concepts): a guide to the underlying concepts and architecture.
* [Developer Guide](http://github.com/cloudfoundry/docs-dev-guide): step-by-step instructions and reference material for developers pushing applications to Cloud Foundry.
* [Services](http://github.com/cloudfoundry/docs-services): information about extending Cloud Foundry with custom services, and the service broker API.
* [Buildpacks](http://github.com/cloudfoundry/docs-buildpacks): a guide to developing your own buildpacks.
* [Loggregator](http://github.com/cloudfoundry/docs-loggregator): a guide to the user application logging subsystem of Cloud Foundry.
* [Deploying Cloud Foundry](http://github.com/cloudfoundry/docs-deploying-cf): instructions for operators deploying Cloud Foundry on various IaaS (AWS, OpenStack, etc.) using BOSH
* [Running Cloud Foundry](http://github.com/cloudfoundry/docs-running-cf): information for operators running Cloud Foundry.
* [BOSH](http://github.com/cloudfoundry/docs-bosh): in-depth documentation on BOSH.
* [Administrator Tools](https://github.com/cloudfoundry/docs-cf-admin): documentation about how to operate Cloud Foundry deployments using bosh and cf command line tools.

## Contributing Pull Requests

To submit a pull request to the documentation, please follow this process:

1. Make sure you have a signed CLA. Even if you aren't contributing running code, we still need a Contributor License Agreement.

2. Clone this repository. (You do not need to fork this repository unless you plan to contribute template changes or add a new topic repository).

3. Fork the topic repository that you want to contribute to. Make sure to clone your fork of the topic repository to a directory that is a sibling to this book repository. So, for example, if you are contributing content to the Buildpack documentation, your folder structure would look like this:

  <pre>

    |
    +-- docs-book-cloudfoundry
    |
    +-- docs-buildpacks
    |
  </pre>

4. Make your changes

5. Run bookbinder on your local changes:

  <pre>
    $ cd docs-book-cloudfoundry
    $ bundle install --binstubs
    $ bin/bookbinder bind local
  </pre>

6. Preview your changes by running the resulting Sinatra app:

  <pre>
    $ cd final_app
    $ bundle
    $ rackup
  </pre>

By default, Bookbinder serves the documentation at http://localhost:9292/

Bookbinder attempts to assemble the doc set from your local copies.
It will skip any topic repositories that you do not have checked out.

Note that Bookbinder will tell you if you have any broken links.
It might report broken links associated with topic repositories that you
do not have on your local machine.

When you are satisfied with your changes, submit your pull request on
the topic repository.

**Note**: Once your pull request is merged, your changes appear on [docs.cloudfoundry.org](http://docs.cloudfoundry.org) the next time the cf-docs team
pushes updates to the production docs. Updates go live at least once a week.


