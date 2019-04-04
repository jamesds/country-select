# Country-Select

_Compatible with Rails 5.2_

Provides a simple helper to get a HTML select list of countries.  The list of countries comes from the ISO 3166 standard.  While it is a relatively neutral source of country names, it may still offend some users.

Users are strongly advised to evaluate the suitability of this list given their user base.

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
