## Danger

[Danger](http://danger.systems) runs during Grape projects' CI process, and gives you a chance to automate common code review chores.

[![Build Status](https://travis-ci.org/ruby-grape/danger.svg?branch=master)](https://travis-ci.org/ruby-grape/danger)

### Setup

Enable Danger for a project within the [ruby-grape organization](https://github.com/ruby-grape).

#### Set DANGER_GITHUB_API_TOKEN in Travis-CI

In Travis-CI, choose _Settings_ and add `DANGER_GITHUB_API_TOKEN` in _Environment Variables_. Set the value to the API key for the [grape-bot](https://github.com/grape-bot) user, look in [this build log](https://travis-ci.org/ruby-grape/danger/builds/148579641) for its value.

#### Add Danger

Add `danger` to `Gemfile`.

```ruby
gem 'danger', '~> 2.0', require: false
```

#### Add Dangerfile

Commit a `Dangerfile` with some placeholder text, eg. [Grape's Dangerfile](https://github.com/ruby-grape/grape/blob/master/Dangerfile). Danger automatically inherits the [Dangerfile](Dangerfile) in the organization's `danger` repo (this repo).

#### Add Danger to Travis-CI

Add Danger to `.travis.yml`, eg. [Grape's Travis.yml](https://github.com/ruby-grape/grape/blob/master/.travis.yml).

```yaml
before_script:
  - bundle exec danger
```

#### Commit via a Pull Request

To test things out, make a dummy entry in `CHANGELOG.md` that doesn't match the standard format and make a pull request. Iterate until green.

## License

MIT License. See [LICENSE](LICENSE) for details.

