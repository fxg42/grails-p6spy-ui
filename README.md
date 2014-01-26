## Why

Forked to fix different runtime errors.

## Installing

    $ gvm use grails 2.0.4
    $ grails refresh-dependencies
    $ grails maven-install

## Usage

Add the plugin dependency in **BuildConfig.groovy** excluding the bundled jQuery
dependency:

    plugins {
      compile (":p6spy-ui:0.2-SNAPSHOT") {
        excludes 'jquery'
      }
    }

Comment out the `driverClassName` property in **DataSource.groovy** and replace
it with the P6Spy driver:

    dataSource {
      development {
        // driverClassName = "org.postgresql.Driver"
        driverClassName = "com.p6spy.engine.spy.P6SpyDriver"
      }
    }

In **Config.groovy**, instruct P6Spy to use the original jdbc driver:

    grails.plugin.p6spy.realdriver = "org.postgresql.Driver"

Start the app and go to [http://localhost:8080/myapp/p6spy].

