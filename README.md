# angular-cli-tutorial
Getting started with [Angular CLI](https://github.com/angular/angular-cli).  

John's Quick How-Tos:
- [Install](#install)
- [Generate New Project](#generate-new-project)
- [Run locally](#run-locally)
- [Build for deployment](#build-for-deployment)
- [Generate Components](#generate-components)
- [Styling Preprocessors](#styling-preprocessors)
- [Unit Test](#unit-test)
- [Code Coverage](#code-coverage)
- [E2E Tests](#e2e-tests)
- [Linting](#linting)
- [Proxying](#proxying)

#Install

Run `npm install -g angular-cli`.

After installation, Angular CLI will be available using the `ng` command.

#Generate New Project

Run `ng new <projectname>`

A directory named after your <projectname> will be created.  There are no prompts when creating a new project.  Instead, the project is scaffolded using sensible defaults.

#Run Locally

New projects can be immediately ran locally without any further setup.

For local deployment, run `ng serve`.

The CLI will utilize webpack to transpile (TS->JS) and compile your source files and static assets.

Open from your browser at `http://localhost:4200`.

#Build for deployment

Run `ng build`.  

The webpacked files will be outputed to your project's `/dist` folder.

These files can then be dropped to any web server to be served.  I recommend tar'ing the files to make exchanging and deploying easier.

#Generate Components

Run `ng generate component <component_name>` to scaffold a new component that generates the following:

- Angular2 code (TypeScript)
- Styling (CSS)
- Template (HTML)
- Unit Test (Spec)

More than just components can be generated.  Try generating the following: `pipe`, `service`, `directive`, and `module`

#Styling Preprocessors

There is a good chance that you'll want to use a CSS preprocessor such as SASS.  Rigging the project for SASS is straightforward and can be done in three simple steps:

1) `npm install --save node-sass`
2) Edit `angular-cli.json`, change "defaults.styleExt" to "scss" and "apps.styles" to ["styles.scss"]
3) Change the file extensions of your components' CSS files from ".css" to ".scss"

That's all there is to it.  The project will now compile SASS down to CSS automagickly. 

#Unit Test

Run `ng test` to get execute unit tests.

The unit test configuration is stored in `karma.conf.js`.

#Code Coverage

Run `ng test --code-coverage` to run unit tests and generate a code coverage report.  The default location that the report is written to is the `/coverage` directory in your project.

#E2E Tests

Run `ng e2e` to run your suite of e2e tests.

The e2e configuration is defined in `protractor.conf.js`.

#Linting

Run `ng lint` to run the typescript linter.

The lint configuration is defined in `tslint.json`.

#Proxy to a backend

It is likely that you will want to connect a backend to the frontend that Angular CLI generated.  One way is to simply hardcode the backend URL in your Angular2 service.  However, this is not very scalable and it would be difficult to manage that URL across environments.  A scalable solution would be to route all backend calls through a single relative path to your back end such as /api/*.   See Angular CLI's documentation for an example on how to do this:

https://github.com/angular/angular-cli#proxy-to-backend
