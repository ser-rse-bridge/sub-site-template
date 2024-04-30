# sub-site-template

## Introduction

This repository is meant to serve as a template (in the GitHub sense) to facilitate setting up
sub-sites of <ser-rse-bridge.github.io> with styling consistent to the main site.  While we can
put any content we want on the main site, there may be some situations where it is useful to put
some content in a separate repository for management purposes.

## Usage

To use this template, simply use the GitHub web user interface to create a new repo using this one 
(ser-rse-bridge/sub-site-template) as a template, and then adjust a few configuration variables and
repository settings.

In `_config.yml`:
* `baseurl` should be set to the sub-site's top level
* `repository` should set to the new org/repo.  This variable is used in "edit this file on GitHub" links.
* `footer.links.url` for the "GitHub" label should be set to the full URL for the new repo.  This variable is used in the GitHub link in the footer.

In the repository Settings > Pages > Build and Deployment section:
* Set Source to `GitHub Actions` to use the `.github/workflows/jekyll.yml` action that's included in the repository.  Using an action is necessary because the site uses Jekyl plugins that are not supported in the "Classic Pages" build approach.

## Notes

This repository contains a modified version of the Minimal Mistakes file `_includes/masthead.html` in which the masthead links (on the logo, title, and subtitle) are directed to the parent site rather than the top of the current site.  This makes the masthead link behavior consistent between the main site and the sub-site.  If you don't want this behavior, delete the modified `masthead.html` file and it will revert to using the Minimal Mistakes default `masthead.html`.  

Also, nothing has been done about navigation links (which are also part of the masthead) since the main site doesn't have any.  If we do start using navigation links, this will require some attention for sub-sites.

Finally, note that if changes are made to the styling of the main site, they'll also need to be made here and in any active sub-sites.  There's no automation that
can magically identify and propagate such changes for us.  Unfortunately.