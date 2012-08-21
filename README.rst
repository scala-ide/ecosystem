Scala IDE ecosystem builds
==========================

This is a set of maven projects used to create the Scala IDE ecosystem update sites.

The projects
------------

The projects contain the following:

stable-scala-ide-2.0-scala-2.9
..............................

**Scala IDE ecosystem stable (Scala IDE 2.0, Scala 2.9.2)**

Contains stable version of plugins for Scala IDE 2.0.2 and Scala 2.9.2.

* Scala IDE 2.0.2 - `website`__

__ scala-ide_

dev-scala-ide-2.0-scala-2.9
...........................

**Scala IDE ecosystem dev (Scala IDE 2.0.2, Scala 2.9.2)**

http://download.scala-ide.org/ecosystem/dev-2.0-2.9/site/

Contains development version of plugins for Scala IDE 2.0.2 and Scala 2.9.2.

* Scala IDE 2.0.2 - `website`__
* ScalaTest plugin for Scala IDE 0.9.2 - `project page`__

__ scala-ide_
__ scalatest plugin_

dev-scala-ide-master-scala-2.9
..............................

**Scala IDE ecosystem dev (Scala IDE 2.1.x, Scala 2.9.x)**

http://download.scala-ide.org/ecosystem/dev-master-2.9/site/

Contains development version of plugins for Scala IDE 2.1.x and Scala 2.9.x.

* Scala IDE 2.1.x - `website`__
* ScalaTest plugin for Scala IDE 0.9.2 - `project page`__
* InSynth code synthesis for Scala IDE nightly - `project page`__

__ scala-ide_
__ scalatest plugin_
__ insynth_

dev-scala-ide-master-scala-trunk
................................

**Scala IDE ecosystem dev (Scala IDE 2.1.x, Scala 2.10.x)**

Contains development version of plugins for Scala IDE 2.1.x and Scala 2.10.x.

* Scala IDE 2.1.x - `website`__
* InSynth code synthesis for Scala IDE nightly - `project page`__

__ scala-ide_
__ insynth_

How to make a plugin of your project
----------------------------------

If you already have an Eclipse plugin version of your project, you can go to the next section to see if it can be added to the ecosystem update sites.

Otherwise, we provide two `giter8`_ templates to generate complete maven projects, with plugins, features and update site:

* `scala-ide/scala-plugin.g8`__ - a set of projects to develop an Eclipse plugin written in Scala.
* `scala-ide/scala-ide-plugin.g8`__ - a set of projects to develop an Eclipse plugin on top of Scala IDE.

__ https://github.com/scala-ide/scala-plugin.g8
__ https://github.com/scala-ide/scala-ide-plugin.g8

You can use them to start the Scala IDE plugin version of your project.

How to add your plugins to the sites
------------------------------------

What content is allowed?
........................

There are no formal rules, and the final decision is let to discretion of the current commiters of the Scala IDE project.

But the basic criteria are:

* it has to be relevant to Scala.
* it has to work well enough to be usable, and not impact in a bad way other plugins.

1st method: clone, modify, pull request (preferred)
...................................................

* send a message to the `dev mailing list`_, to check if we are likely to accept your contribution.

  

* clone the repository
* select the update site(s) you want to add your plugin to.
* in ``site.xml``:

  * add your code feature in the relevant category.
  * create a new category if that make sense.
  * add your source feature in the source category.

* in ``pom.xml``:

  * create a property with the location of your update site.
  * create a repository entry for your update site.

* run the build locally.
* check that installing your plugin using the local update site works correctly.
* create a pull request.
* wait for the comments on the pull request.
* modify or argue on the comments.
* after request as been merged, and the site(s) rebuilt, check that installing your plugin using the update site works correctly.

  

* improve this documentation and submit a pull request to help your fellow contributors.

2nd method: providing us the relevant information (may take an infinite time)
.............................................................................

* create a `ticket`_ asking nicely for your plugin to be added.
* provide the name of the feature(s), version number(s), the update site(s) and the category it could be added in.
* wait for one of the contributors to take the time to look at the ticket and make the appropriate changes.
* answer swiftly to any request for additional information.
* wait more.
* when the ticket is fixed, and the site(s) rebuilt, check that installing your plugin using the update site works correctly.

.. _dev mailing list: http://scala-ide.org/docs/user/community.html
.. _ticket: http://scala-ide.org/docs/user/community.html
.. _giter8: https://github.com/n8han/giter8/

.. _scala-ide: http://scala-ide.org/
.. _scalatest plugin: https://github.com/scalatest/scalatest-eclipse-plugin
.. _insynth: https://github.com/kaptoxic/scala-ide-insynth-integration/tree/master/ch.epfl.insynth.build