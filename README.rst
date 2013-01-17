Scala IDE ecosystem builder
===========================

This is the ecosystem builder, a `Maven <https://maven.apache.org/>`_
project that uses the Scala-IDE `build
tools <https://github.com/scala-ide/build-tools>`_ to build and
integrate Scala-related plugins within Eclipse update sites, on top of
specific **flavors** of Eclipse, Scala and Scala-IDE.

The latest version of the source for this project is hosted on:
`https://github.com/scala-ide/ecosystem <https://github.com/scala-ide/ecosystem>`_

Legacy
------

The ``stable-scala-ide-2.0-scala-2.9/`` folder contains a legacy version
of the ecosystem builder project. This project is necessary only to
build plugins for Scala-IDE version <= 2.0.2. Its documentation has been
relegated to ``stable-scala-ide-2.0-scala-2.9/README.old.rst``.

How to create an Eclipse plugin from your Scala project
-------------------------------------------------------

If you already have an Eclipse plugin version of your project, you can
go to the next section to see if it can be added to the ecosystem update
sites.

Otherwise, we provide two `giter8 <https://github.com/n8han/giter8>`_ templates to generate complete
maven projects, with plugins, features and update site:

-  `scala-ide/scala-plugin.g8 <https://github.com/scala-ide/scala-plugin.g8>`_
   a set of projects to develop an Eclipse plugin written in Scala

-  `scala-ide/scala-ide-plugin.g8 <https://github.com/scala-ide/scala-ide-plugin.g8>`_
   a set of projects to develop an Eclipse plugin on top of Scala IDE.

You can use them to start the Scala IDE plugin version of your project.

How to contribute a plugin to the ecosystems distributed by the Scala-IDE team
------------------------------------------------------------------------------

You have a **fantastic** plugin that you want to see in the ecosystem ?
Please contact us ! Though we retain final editorial control on what
plugins we choose to integrate to the Scala-IDE ecosystems, we are very
eager to integrate plugins that are:

-  generally awesome

-  of broad relevance to the Scala developer community

-  quality, well-maintained code

Naturally, **the distribution of the plugin by the Scala-IDE team has to
be permitted within the framework of the plugin's license**.

Getting your plugin sponsored [1]_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To get your plugin sponsored, you need to look for a sponsor from the
`Scala-IDE team <http://scala-ide.org/team.html>`_ on the `Scala-IDE
development mailing
list <http://groups.google.com/group/scala-ide-dev>`_, ensuring your
request includes:

-  a link to the sources of your project

-  a link to the plugin's documentation

-  a link to the plugin's bug tracker (or equivalent)

-  a link to the p2 repository

-  a link to the project's website (Optional)

When the sponsor has indicated the plugin is ready for inclusion, you
can make sure it is set up to build against the ecosystem's ``base``
repositories (see technical steps in `the next section <#sec-1-3-2>`_).
The final step is to create a pull request against the `ecosystem
project <https://github.com/scala-ide/ecosystem>`_ to provide a `feature
file <https://github.com/scala-ide/ecosystem/wiki/Configuration#Add-ons-configuration>`_,
a configuration file for the ecosystem builder that summarises the
information from your sponsor demand above, and lets the ecosystem
builder pick up your project during re-builds.

That's it ! The ecosystem also offers some
`facilities <https://github.com/scala-ide/ecosystem/wiki/Plugin-maintenance-and-update>`_
for monitoring the compatibility of your plugin against upcoming
Scala-IDE versions, see the documentation wiki for details.

Getting your plugin to build [2]_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

While most Scala-related projects interface against either
`Scala <http://www.scala-lang.org/>`_ or
`Scala-IDE <http://scala-ide.org/>`_ code, neither parent project
provides a stable public API. Hence, the requirement across Scala-IDE
ecosystems is that plugins have strict version dependencies for
Scala-IDE and Scala. To set those specific dependencies automatically,
we provide tools to **instrument your build**.

For that, you need to have as many built artifacts as there are flavors
of the Eclipse × Scala × Scala-IDE toolchain that you want to support.
Each build needs to include a `Maven profile we
provide <https://github.com/scala-ide/ecosystem/wiki/Providing-add-ons#Strict-version-dependencies>`_
to set up your artifact's ``Manifest``. An example of how to achieve
that without too much pain is a `build
script <https://github.com/scalatest/scalatest-eclipse-plugin/blob/master/ecosystem-build.sh>`_
from the `Scala-Test
plugin <https://github.com/scalatest/scalatest-eclipse-plugin>`_.

Once this is done, you need to provide a pull request against the
`ecosystem project <https://github.com/scala-ide/ecosystem>`_ that adds
a `feature
file <https://github.com/scala-ide/ecosystem/wiki/Configuration#Add-ons-configuration>`_
in our `features directory <https://github.com/scala-ide/ecosystem/tree/master/features>`_
for your plugin, as described above.

Getting Support and advice
--------------------------

You can find support in the `Scala-IDE development mailing
list <https://groups.google.com/forum/#!forum/scala-ide-dev>`_. We
welcome your comments and questions, including those related to this
README !

.. [1]
   This section is a condensed version of the
   `Contributor's guide <https://github.com/scala-ide/ecosystem/wiki/Contributor-guide>`_ present in the project's
   `documentation wiki <https://github.com/scala-ide/ecosystem/wiki>`_.

.. [2]
   This section is a condensed version of the
   `Contributor's cheatsheet <https://github.com/scala-ide/ecosystem/wiki/Contributor%2527s-cheatsheet>`_ present in the project's
   `documentation wiki <https://github.com/scala-ide/ecosystem/wiki>`_.
