# Country-Select

_Compatible with Rails 5.2_

Provides a simple helper to get a HTML select list of countries.  The list of countries comes from the ISO 3166 standard.  While it is a relatively neutral source of country names, it may still offend some users.

Users are strongly advised to evaluate the suitability of this list given their user base.

## Release Process

This Gem is owned and managed by the Core Services team. Released to [github packages](https://github.com/fac/country-select/packages).

Packaging is handled by Jenkins, to push a new release:

* Create a PR that increases the version in `version.rb`.
* Get that reviewed and approved.
* Merge, on successful build Jenkins will package the gem and release it to github packages.
* Update the bundles for any applications using this gem.

You can track builds in slack, [#country-select-ci](https://freeagent.slack.com/channels/country-select-ci). Track releases in [#gem-release](https://freeagent.slack.com/channels/gem-release).

See [Internal Gems](https://www.notion.so/freeagent/Internal-gems) for more detail.

## Installation

Install as a gem using

    gem install country-select

Or put the following in your Gemfile

    gem 'country-select'

## Example

Simple use supplying model and attribute as parameters:

    country_select("user", "country_name")

Supplying priority countries to be placed at the top of the list:

    country_select("user", "country_name", [ "United Kingdom", "France", "Germany" ])
    
Supplying additiontal options:

    country_select("user", "country_name", [ "United Kingdom", "France", "Germany" ], {:prompt => "Choose Country"}, {:class => "country-chooser"})

Using together with `form_for` or `fields_for`:

    <%= form_for @user do |f| %>
      <%= f.country_select("country_name") %>
    <% end %>

Copyright (c) 2008 Michael Koziarski, released under the MIT license
