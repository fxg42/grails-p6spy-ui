## Why

Forked to fix different runtime errors.

## Installing

    $ gvm use grails 2.0.4
    $ grails refresh-dependencies
    $ grails maven-install

## Usage

    plugins {
      compile (":p6spy-ui:0.2-SNAPSHOT") {
        excludes 'jquery'
      }
    }
