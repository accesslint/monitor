[![Build Status](https://travis-ci.org/accesslint/monitor.svg)](https://travis-ci.org/accesslint/monitor)

# Accessibility Monitoring for Your Website

accesslint.js warns you of accessibility errors in your website.

## Usage

Download the compiled library from the releases page or build it yourself. Then,
include the javascript in you page:

```
<script src="accesslint.js" type="text/javascript">
```

## How it works

When a visitor arrives at a page that has the script installed, an audit will
run in the background automatically. If there are any accessibility issues on
that page, accesslint.js will log the error to the console, and post to a server
endpoint that you can optionally configure.

accesslint.js runs assertions from the
[aXe-core](https://github.com/dequelabs/axe-core) accessibility library wherever
you include the script. It the logs the violations the browser's Javascript
console. It also POSTs the results to `/access_lint/errors` in your app. If you
set up and endpoint with that path, you can log the errors on the server too.
See [AccessLint::Rails](https://github.com/thoughtbot/access_lint-rails) for a
Rails implementation of server side logging of accessibility errors.

## Development

AccessLint Monitor uses babel and webpack to transpile and package ES2015
code for inclusion clientside. It uses karma and mocha to run tests.

### Setup

    $ bin/setup

### Testing

    $ gulp

### Building

#### Development

    $ gulp build-dev # build and watch for changes

#### Production

    $ gulp build
