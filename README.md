# Country-Select

Provides a simple helper to get an HTML select list of countries.  The list of countries comes from the ISO 3166 standard.  While it is a relatively neutral source of country names, it may still offend some users.

Users are strongly advised to evaluate the suitability of this list given their user base.

## Latest Changes

**1.1.1**

- Fixed incompatibility with Rails 3.2.2 (thanks to [jmazzi](https://github.com/jamesds/country-select/pull/4))

**1.1.0**

- Updated the country list to change the name of *Libyan Arab Jamahiriya* to *Libya* according to the [latest ISO 3166 newsletter](http://www.iso.org/iso/nl_vi-11_name_change_for_libya.pdf)
- A country in the priority list will be selected there and not in the main list (thanks to [yyyc514](https://github.com/jamesds/country-select/pull/3))
- Removed relics from the pre-gem days

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
      

## Version History

 - **1.0.5** - runtime error raised if any of the user-supplied priority countries do not correlate with those in the main country list.
 - **1.0.4** - updated the country list to match the latest ISO 3166 specification
 - **1.0.3** - changed gem name from 'iso-3166-country-select' to just 'country-select'
 - **1.0.2** - forked the plugin and made it into a gem

Copyright (c) 2008 Michael Koziarski, released under the MIT license
