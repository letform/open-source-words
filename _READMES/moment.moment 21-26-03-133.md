a lightweight javascript date library for parsing validating manipulating and formatting dates documentation port to ecmascript 6 version 2 10 0 moment 2 10 0 does not bring any new features but the code is now written in ecmascript 6 modules and placed inside src previously moment js locale js and test moment js test locale js contained the source of the project now the source is in src temporary build ecmascript 5 files are placed under build umd for running tests during development and the moment js and locale js files are updated only on release if you want to use a particular revision of the code make sure to run grunt transpile update index so moment js and locales js are synced with src we might place that in a commit hook in the future upgrading to 2 0 0 there are a number of small backwards incompatible changes with version 2 0 0 see the full descriptions here changed language ordinal method to return the number ordinal instead of just the ordinal changed two digit year parsing cutoff to match strptime removed moment sod and moment eod in favor of moment startof and moment endof removed moment humanizeduration in favor of moment duration humanize removed the lang data objects from the top level namespace duplicate date passed to moment instead of referencing it changelog contributing were looking for co maintainers if you want to become a master of time please write to ichernev in addition to contributing code you can help to triage issues this can include reproducing bug reports or asking for vital information such as version numbers or reproduction instructions if you would like to start triaging issues one easy way to get started is to subscribe to moment moment on codetriage license moment js is freely distributable under the terms of the mit license