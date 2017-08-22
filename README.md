[![Build Status](https://travis-ci.org/cucumber/cucumber-ruby-wire.svg?branch=master)](https://travis-ci.org/cucumber/cucumber-ruby-wire)

# cucumber-wire

## Configuration

You can configure the connection using a YAML file called a `.wire` file:

```yaml
host: localhost
port: 54321
timeout:
  connect: 11
  invoke: 120
  begin_scenario: 120
  end_scenario: 120
```

### Timeouts

The default timeout is 120 seconds. `connect` has a default timeout of 11 seconds.

### YAML with ERB templating

The file format is YAML, with ERB templating, so you could make the configuration configurable:

```yaml,erb
host: localhost
port: 54321
timeout:
  connect: <%= (ENV['MY_CONNECT_TIMEOUT'] || 11).to_i %>
  invoke: 120
  begin_scenario: 120
  end_scenario: 120
```
