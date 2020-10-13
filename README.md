# kpn-style

kpn shared style configs.

## Installation

Add this line to your application's Gemfile:

```ruby
group :test, :development do
  gem 'kpn-style'
end
```

Or, for a Ruby library, add this to your gemspec:

```ruby
spec.add_development_dependency 'kpn-style'
```

And then run:

```bash
$ bundle install
```

## Usage

Create a `.rubocop.yml` with the following directives:

```yaml
inherit_gem:
  kpn-style:
    - ruby-2.1.yml
```

Or for Ruby 2.4:

```yaml
inherit_gem:
  kpn-style:
    - ruby-2.4.yml
```

Or for Ruby 2.5:

```yaml
inherit_gem:
  kpn-style:
    - ruby-2.5.yml
```

Now, run:

```bash
$ bundle exec rubocop

or

$ rake rubocop
```

You do not need to include rubocop directly in your application's dependencies. kpn-style will include a specific version of `rubocop` and `rubocop-rspec` that is shared across all projects.

## Style overrides

Sometimes you need to override style rules. RuboCop have a nice inheritance hierachy so you can override the default settings.
The hierachy is:

```
inherit_gem -> inherit_from -> local rules
```

For example:

```yaml
inherit_gem:
  kpn-style:
    - ruby-2.1.yml

inherit_from: .rubocop_todo.yml

AllCops:
  Exclude:
    - exclude/file.rb
```

## Update gem

1. Update the ruby-2.X.yml file
2. Update the version parameter `spec.version` in the `kpn_style.gemspec`
3. Tag the release: `git tag VERSION`
4. Push changes: `git push --tags`
5. Update the release notes on GitHub.com
6. Build and publish:

```bash
gem build kpn_style.gemspec
gem push kpn-style-x.x.x.gem
```

To push gems to rubygems.org you can use a `~/.gem/credentials` with the `rubygems_api_key`. You can find a small how to on the Profile edit page https://rubygems.org/profile/edit in the section `API ACCESS`.

### Special thanks

A special thanks to https://github.com/percy/percy-style/ for the idea and template of this Gem.
