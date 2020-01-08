# aem-unit-tests-sample

This is a sample project to provide guidance on the implementation of Unit tests on AEM Development.

## Modules

The main parts of the template are:

* core: Java bundle containing all core functionality like OSGi services, listeners or schedulers, as well as component-related Java code such as servlets or request filters.
* ui.apps: contains the /apps (and /etc) parts of the project, ie JS&CSS clientlibs, components, templates, runmode specific configs as well as Hobbes-tests
* ui.content: contains sample content using the components from the ui.apps

## How to build

To build all the modules run in the project root directory the following command with Maven 3:

    mvn clean install

If you have a running AEM instance you can build and package the whole project and deploy into AEM with

    mvn clean install -PautoInstallPackage -Padobe-public

Or to deploy it to a publish instance, run

    mvn clean install -PautoInstallPackagePublish -Padobe-public

Or alternatively

    mvn clean install -PautoInstallPackage -Daem.port=4503 -Padobe-public

Or to deploy only the bundle to the author, run

    mvn clean install -PautoInstallBundle -Padobe-public

## Testing

There are three levels of testing contained in the project:

* unit test in core: this show-cases classic unit testing of the code contained in the bundle. To test, execute:

    mvn clean test
