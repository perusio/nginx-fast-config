# Nginx Fast Config

## Introduction

**Nginx Fast Config** is a Drupal 6 only module that disables the
**deslash** setting of the
[globalredirect](http://drupal.org/project/globalredirect)
module. This setting causes a redirect loop with a 0 rewrites
[Nginx configuration](https://github.com/perusio/drupal-with-nginx). There's
no need for this setting to be enabled &mdash; which is the
**default** &mdash; since the way Nginx processes the requests **removes** the
trailing slash.

The deslash setting in the `globalredirect` settings form at
`/admin/settings/globalredirect` is removed from the form.

## Installation

To use this module you must have the `globalredirect` module
installed. After installing the module clear the cache. The preferred
way of doing that is through [drush](http://drupal.org/project/drush),
with `drush cc all`.

After that you're ready and set to go. There will appear a setting at
the `/admin/reports/status` status page stating that it's safe to run
the 0 rewrites configuration.

## Drupal 7

There will never be a drupal 7 version of this module. The drupal 7
version of `globalredirect` doesn't provide this setting of removing
the trailing slash. Since drupal already does that in
[`request_path()`](http://api.drupal.org/api/drupal/includes--bootstrap.inc/function/request_path/7). Therefore
it's safe to use the
[Nginx Fast Config](https://github.com/perusio/drupal-with-nginx) with
drupal 7 in general. Of course Your Mileage May Vary.

## Further developments

If there's any other module that causes problems with the 0 rewrites
configuration please let me know in the
[github issue queue](https://github.com/perusio/drupal-with-nginx/issues)
or here.
