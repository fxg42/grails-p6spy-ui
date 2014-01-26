## Why

Forked to fix different runtime errors.

## Installing

    $ gvm use grails 2.0.4
    $ grails refresh-dependencies
    $ grails maven-install

## Usage

**BuildConfig.groovy**

    plugins {
      compile (":p6spy-ui:0.2-SNAPSHOT") {
        excludes 'jquery'
      }
    }

**DataSource.groovy**

    dataSource {
      development {
        // driverClassName = "org.postgresql.Driver"
        driverClassName = "com.p6spy.engine.spy.P6SpyDriver"
      }
    }

**Config.groovy**

    grails.plugin.p6spy.realdriver = "org.postgresql.Driver"
