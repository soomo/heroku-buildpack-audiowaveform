Heroku buildpack: audiowaveform
=======================


This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using audiowaveform in core.
It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Lineage
-------

Shamelessly forked from the [audiowaveform heroku buildpack](https://github.com/Mattchewone/heroku-buildpack-audiowaveform) by [Matt Chaffe](https://github.com/Mattchewone).

Usage
-----
To use this buildpack, you should prepare a .buildpacks file that contains this buildpack url and your real buildpack url:

    $ ls
    .buildpacks
    ...

    $ cat .buildpacks
    https://github.com/soomo/heroku-buildpack-audiowaveform

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

You can verify that sox is installed by calling:

    $ heroku run "audiowaveform"
