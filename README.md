# serverless-plugin-scripts [![npm version](https://img.shields.io/npm/v/serverless-plugin-scripts.svg)](https://www.npmjs.com/package/serverless-plugin-scripts)

Add scripting capabilities to the [Serverless Framework](https://serverless.com/framework/).

## Caution

**This project is in maintenance mode, and it will not get any new features.**

## Installation

Install the plugin in your Serverless (v1.0 or higher) project:

```
npm install --save serverless-plugin-scripts
```

And activate it by adding the following configuration to your `serverless.yml` file:

```yaml
plugins:
  - serverless-plugin-scripts
```

## Usage

### Custom commands

To add a custom command to the Serverless CLI, just define a `custom.scripts.commands` property in your `serverless.yml` file:

```yaml
custom:
  scripts:
    commands:
      hello: echo Hello from ${self:service} service!
```

You can now run `serverless hello` to execute the `hello` command.

### Simple hooks

It is possible to define simple hooks for existing Serverless CLI commands by adding a `custom.scripts.hooks` property in your `serverless.yml` file:

```yaml
custom:
  scripts:
    hooks:
      'package:createDeploymentArtifacts': npm run compile
```

The next time you run `serverless deploy`, your script will be automatically invoked during the `deploy:createDeploymentArtifacts` lifecycle event.

To find out about existing lifecycle events, check out [this page](https://gist.github.com/HyperBrain/50d38027a8f57778d5b0f135d80ea406).

## Author

Created and maintained by [Manuel Vila](https://github.com/mvila).

## License

MIT
