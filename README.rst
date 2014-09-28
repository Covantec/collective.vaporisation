.. contents::

Introduction
============

The ``collective.vaporisation`` addons for Plone give to the user a tag cloud portlet.

    A tag cloud (or weighted list in visual design) is a visual depiction of keywords used
    into your site. Tags are usually single words and are normally listed alphabetically,
    and the importance of a tag is shown with font size. Thus, it is possible to find a tag
    alphabetically and by popularity.
    The tags are hyperlinks that lead to a collection of contents that are associated with a keyword.
    This hyperlinks makes a Plone search that show the list of contents marked with the keyword selected.

    -- Definition of tag cloud `from Wikipedia`__

__ http://en.wikipedia.org/wiki/Tag_cloud

.. figure:: http://blog.redturtle.it/pypi-images/collective.vaporisation/collective.vaporisation-screenshot-1
   :alt: MoNet MultimediaMO tagcloud

   Big tagcloud used in a collective.portletpage area

.. figure:: http://blog.redturtle.it/pypi-images/collective.vaporisation/collective.vaporisation-screenshot-2
   :alt: CCFE site tagcloud portlet

   With some CSS rules you can customize colors

An advanced feature is the "*join navigation*" that allows user to make a search related and sequential.
During the search the view of the portlet is different. One first part of it shows only the keywords
into the contents that are result of the search. A second one show the selected tags allowing user to
remove some of them from the search.

Usage
=====

When you add this kind of portlet, named "Tagcloud portlet", you're in front of an
edit form with many fields.

We see in detail what they do:

`Name to display`
     The name of the tag cloud. For display purposes.
`Number of different sizes`
     This number will determine the biggest size.
`Number of keywords to display`
     This number indicate the max number of keywords shown. The value 0 (zero) show  all the keywords.
`Cloud reload timeout`
     Time in minutes after which the cloud should be reloaded. This time isn't the only parameter that
     force the reload of cloud.
     Put this value to "0" for disabling caching (**don't do this on production**).
`Start path`
     Only the objects under this directory will be taken in consideration.
     If empty (default), the portlet will search in all the site.
`Indexes to use`
     In this field you can select the indexes to use.
     We can use all the KeywordIndex defined into your site.
     The default one is "Subject" index of Plone.
`Type of contents`
     We can filter the objects by type.
     Only the objects of the selected types will be used to search the keywords.
`Activate joint navigation`
     With this options active the portlet change his view to show only the related keywords.
     This will be seen during the functionality of search of contents with some keywords.
`Use only the keywords of this list`
     A whitelist for a manual choise of the keywords to show.
     Remove from keywords list:
     A blacklist for remove some keywords from the shown.
`Mode to use`
     Select a mode of use among those diponibile.
     Now we have only one mode of use. Other one can be implementated by external package
     through an adapter.
`Sort keywords`
     If actived, the keywords will be sorted alphabetically.

TODO and know issues
====================

- If you're using more than one tag cloud portlet you have to remind to use different name. In this way,
  the "join navigation" will be applied only to the portlet where the user clicks over a keyword.
- The list of keywords used into the edit form doesn't change dinamically when the filters change
  To use the whitelist or the blacklist after a change to one of field used to filter the contents
  (like "*Start path*", "*Indexes to use*" and "*Type of contents*") you need to save the portlet and
  re-enter into edit.

  During the load of edit form the vocabularies will be recreated.

Dependencies
============

Tested on:

* Plone 3.3
* Plone 4.0
* Plone 4.1
* Plone 4.2
* Plone 4.3

Installation
============

Production site
---------------

As usual in your ``zc.buildout`` configuration, you can install ``collective.vaporisation``
by adding it to your buildout: ::

  [buildout]

  ...

  eggs =
      collective.vaporisation

and then running ``bin/buildout``.

Development site
----------------

Optionality, the development package at Github comes with a suitable ``buildout.cfg``.
See `Source Code`_. You just need to clone that repository and play the usual commands
``python bootstrap.py`` + ``bin/buildout``.

Later you can run the Zope instance and create a new Plone site to enabled this package
for use.

Translations
============

This product has been translated into

- Italian translation by:

  - Mirco Angelini <mirco.angelini@redturtle.it>.

  - Andrea Cecchi <andrea.cecchi85@gmail.com>.

- Brazilian Portuguese translation by:

  - Rafahela Garcia Bazzanella <rafahela@gmail.com>

This product isn't translate into your language? please, join to
`Plone transifex organization`_ and helps translate this product
into your language.

Credits
=======

Developed with the support of:

* `Rete Civica Mo-Net - Comune di Modena`__

  .. image:: http://www.comune.modena.it/grafica/logoComune/logoComunexweb.jpg
     :alt: Comune di Modena - logo

* `Camera di Commercio di Ferrara`__

  .. image:: http://www.fe.camcom.it/cciaa-logo.png/
     :alt: Comune di Modena - logo

All of them supports the `PloneGov initiative`__.

__ http://www.comune.modena.it/
__ http://www.fe.camcom.it/
__ http://www.plonegov.it/

Authors
=======

This product was developed by RedTurtle Technology team.

.. image:: http://www.redturtle.it/redturtle_banner.png
   :alt: RedTurtle Technology Site
   :target: http://www.redturtle.it/

Original idea and code came from Souheil Shelfouh, that made `vaporisation`__ product

__ http://plone.org/products/vaporisation

Contribute
==========

- Issue Tracker: https://github.com/RedTurtle/collective.vaporisation/issues
- Source Code: https://github.com/RedTurtle/collective.vaporisation
- Documentation: https://github.com/RedTurtle/collective.vaporisation/blob/master/README.rst

.. _Plone transifex organization: https://www.transifex.com/projects/p/plone/
.. _Source Code: https://github.com/RedTurtle/collective.vaporisation