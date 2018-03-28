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

Now, run:

```bash
$ bundle exec rubocop
```

You do not need to include rubocop directly in your application's dependencies. kpn-style will include a specific version of `rubocop` and `rubocop-rspec` that is shared across all projects.
