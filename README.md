# geoportal-cli

The geoportal-cli is a cross-platform starting point for creating and configuring [Geoportal 2](https://github.com/punkave/geoportal) projects, providing a simple boilerplate generator and wrapping other useful functions into an easy to use command line tool.

First, install geoportal-cli as a global NPM module:
```bash
npm install -g geoportal-cli
```

To view the available commands in a given context, execute the newly-installed command with no arguments:
```bash
geoportal
```

#### Create a project

To create a new project with the tool:
```bash
geoportal create-project <shortname-without-spaces>
```

This will create a local copy of our standard [Geoportal Boilerplate](https://github.com/punkave/geoportal-boilerplate).

If you run the `create-project` command with the `--setup` flag, the command will also `npm install` the dependencies for the project and run `geoportal-users:add` to create an admin user for the CMS, resulting in a fully bootstrapped project. This command will prompt you for a password for the admin user being created.

#### Create a widget
To bootstrap the necessary files and basic configuration for a new Geoportal widget, run the following command from within your Geoportal project's root directory:
```bash
# "-widgets" will automatically be appended to the end of your module name
geoportal create-widget fancy-button
```

#### Create a piece
To bootstrap the necessary files and basic configuration for a new Geoportal piece type, run the following command from within your Geoportal project's root directory:
```bash
# be sure to use the SINGULAR version of the name of your content type
geoportal create-piece vegetable
```

If you run the `create-piece` command with the `--pages` flag, the command will also set up a corresponding pieces-pages module with your new piece type. Similarly, you can run the `create-piece` command with the `--widgets` flag, which will also set up a corresponding pieces-widgets module along with your new piece type. These flags can be used together or separately.

```bash
geoportal create-piece vegetable --pages --widgets
```

#### Create an empty Geoportal module
To bootstrap the necessary files and basic configuration for a brand-new Geoportal module that doesn't extend one of the usual suspects like pieces or widgets:
```bash
geoportal create-module <module name>
```

#### Run other Geoportal-flavored command-line tasks

To run an Geoportal command-line task with the geoportal-cli, which are conventionally run like this: `node app.js <namespace>:<task name>`, you may instead execute the following from any location within a project's directory:
```bash
geoportal <namespace>:<task name>
```

The geoportal-cli assumes the `geoportal` namespace when executing tasks. This means that if a task is in the `geoportal` namespace (such as the `geoportal:reset` task), you can simply execute:
```bash
geoportal <task name>
```

For more information on command-line tasks in Geoportal, visit the [Command line tasks](http://geoportalcms.org/docs/modules/geoportal-tasks/index.html) documentation for Geoportal.

---------------

For more documentation on Geoportal, visit the [A2 documentation site](http://geoportalcms.com).
