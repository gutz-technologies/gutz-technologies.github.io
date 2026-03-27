## Building


To run the theme locally, navigate to the theme directory and run:

```
bundle install
```

To start the Jekyll local development server.

```
bundle exec jekyll serve --watch --verbose
```

To build the theme.

```
bundle exec jekyll build
```

## Deployment

### Github Pages

This theme has been tested to work with Github Pages (and Github Project Pages). When using Github Pages you will need to update the `baseurl` in the `_config.yml` otherwise all the css, images and paths will be broken.

For example the site https://zerostaticthemes.github.io/jekyll-serif-theme would have `baseurl: "/jekyll-serif-theme/"`
