Release notes
=============


Release plan
------------

**UPCOMING ⏳**

- **0.14.x** New visual editor? REST API? Post your ideas on `GitHub Discussions <https://github.com/django-wiki/django-wiki/discussions>`__.
- **0.13.x** Update bootstrap to v5, if you are interested in this work, please help us out - see :url-issue:`1358`.

**DONE 🏁**

- **0.12.x** Adds Django 5.2 support and Python 3.13, drops Django 3.2
- **0.11.x** Adds Django 5.x support and Python 3.12.
- **0.10.x** Uses Hatch as the new build system and has upgrades for Django 4.x and Python 3.11.
- **0.9.x** Definitely Removes Python 3.5 and 3.6 support.
- **0.7.x** Removes Django 2.1 support, adds Django 3.1, 3.2.
- **0.6.x** Targets Bootstrap v4.
- **0.5.x** Remove Django 1.11 support, adds Django 2.2 and 3.x support. Python 3.5+.
- **0.4.x** supports Django 1.11 and Django 2.1 and Python 3.4+.
- **0.3.x** series suppors Django 1.11. As with the upstream Django release, 0.3 was be the last series with Python 2.7 support.

0.12.0
------

Released on 2025-05-01

Added
~~~~~

* Django 5.2 and Python 3.13 support :url-issue:`1393` (Daniel Grießhaber)

Removed
~~~~~~~

* Django 3.2 support :url-issue:`1393` (Daniel Grießhaber)


0.11.2
------

Released on 2024-08-21

Added
~~~~~

* Django 5.1 support :url-issue:`1372` (Benjamin Balder Bach)

Fixed
~~~~~

* Development environment Windows issues :url-issue:`1359` (Oscar Cortez)

Changed
~~~~~~~

* CSS artifacts are automatically built in the Hatch environment :url-issue:`1363` (Oscar Cortez)


0.11.1
------

Released on 2024-04-10

Fixed
~~~~~

* Markdown upgrade caused regressions in relative `wiki:` links :url-issue:`1359` (Henrik Hørlück Berg)


0.11
----

Released on 2024-03-21

Added
~~~~~

* ``[TOC]`` Markdown extension now accepts several arguments, ``toc_depth``, ``title`` and more :url-issue:`1304` (Ryan Henrichson)
* Pymdown-extensions support is gradually added:

  * `PyMDown Blocks <https://facelessuser.github.io/pymdown-extensions/extensions/blocks/>`__ are now supported :url-issue:`1316` (Ryan Henrichson)
  * Sidebar documentation for new plugin (enable by adding ``wiki.plugins.pymdown.apps.PyMdownConfig`` to your installed apps :url-issue:`1334` (Ryan Henrichson, Benjamin Balder Bach)

* Add support for Django 5.0 :url-issue:`1337` (Benjamin Balder Bach)
* Add support for Python 3.12 :url-issue:`1337` (Benjamin Balder Bach)
* Markdown 3.4, 3.5 and 3.6 support :url-issue:`1313` (Ryan Henrichson)

Fixed
~~~~~

* Fix xframe_options_sameorigin bug in MergeView :url-issue:`1294` (liuxiawei 刘夏唯)
* Read the Docs configuration, setup and theme upgraded (Benjamin Balder Bach)
* CodeCov setup restored  :url-issue:`1295` (Oscar Cortez)
* Editsection plugin: Relax path regex (fixing NoReverseMatch) + tests :url-issue:`1299` (Chris Vigelius)
* Fixed extending ``WIKI_MARKDOWN_HTML_WHITELIST`` :url-issue:`1314` (Ryan Henrichson)

Changed
~~~~~~~

* ``align`` attributes in ``<td>`` tags are allowed in generated HTML  :url-issue:`1320` (yengip)
* Codebase linted with ruff (Black and flake8 removed) :url-issue:`1321` (Oscar Cortez)
* Dependencies bumped:

  * django-nyt 1.4
  * django-mptt 0.16
  * Markdown 3.5

* Dependency added:

  * pymdown-extensions 10.5

Translations
~~~~~~~~~~~~

* Nothing updated in this release - `contribute on Transifex <https://www.transifex.com/django-wiki/django-wiki/>`__.


Removed
~~~~~~~

* Removes support for Django 2.2, 3.0, 3.1
* Removes support for Python 3.7, 3.8, 3.9


0.10.1
------

Released on 2024-03-16

Security
~~~~~~~~

* Fixes reDOS issues: Denial of Service possible through unsafe regular expressions `GHSA-wj85-w4f4-xh8h <https://github.com/django-wiki/django-wiki/security/advisories/GHSA-wj85-w4f4-xh8h>`__ (Santos Gallegos, Benjamin Balder Bach)


0.10
----

Released on 2023-05-15

Changed
~~~~~~~

* Removed sqlite database and use fixtures :url-issue:`1260` (Oscar Cortez)
* Improved settings and middleware for demo :url-issue:`1267` (Oscar Cortez)
* Updated languages and use the new Transifex client with Docker (Benjamin Balder Bach)
* Updated django requirement from <4.2,>=2.1 to >=2.1,<4.3 :url-issue:`1275` (Oscar Cortez)
* Upgraded for Sphinx 6 on Read the Docs :url-issue:`1270` (Benjamin Balder Bach)
* Improved Read The Docs configuration :url-issue:`1283` (Oscar Cortez)

Added
~~~~~

* New milestone for v0.11 (https://github.com/django-wiki/django-wiki/milestone/13)
* Added support for the latest Bleach package version :url-issue:`1264` (Oscar Cortez)
* Added environments for Python 3.11 and Django 4.1 :url-issue:`1265` (Oscar Cortez)
* Use the new Transifex client in Docker :url-issue:`1284` (Benjamin Balder Bach)
* Improve discussion forms :url-issue:`1262` (Oscar Cortez)

Fixed
~~~~~

* Bleach is deprecated :url-issue:`1259` (Oscar Cortez)
* TypeError: unsupported operand type(s) for +: 'frozenset' and 'list' :url-issue:`1257` and :url-issue:`1251`  (Oscar Cortez)
* Editing the demo without a login :url-issue:`1263` (Oscar Cortez)
* jQuery broken on docs pages :url-issue:`1281` (Benjamin Balder Bach)
* Solve yml issues and improve issue templates :url-issue:`1261` (Oscar Cortez)
* Fix Release Date for 0.10b1 :url-issue:`1282` (Thomas Rinklin)

0.10b1
------

Released on 2023-01-25

Welcome onboard to new co-maintainer `Oscar Cortez <https://github.com/oscarmcm>`__ 🎉️

Changed / added
~~~~~~~~~~~~~~~

* "Edit Section" plugin fixed and patterns for finding headings rewritten :url-issue:`1247` :url-issue:`1246` (Chris Vigelius)
* Python 3.11 compatiblity: Fix "global flags not at the start of the expression" :url-issue:`1243` (Benbb96)
* Removed direct dependency on ``tinycss2``, inherited from ``bleach`` - due to old versions of pip unable to resolve
* Pass current revision to ``Editor.get_widget()`` and ``get_admin_widget()`` :url-issue:`1249` (Chris Vigelius)
* Refactor package setup to use ``pyproject.toml`` and `Hatch <https://pypi.org/project/hatch/>`__ :url-issue:`1227` (Oscar Cortez)

Fixed
~~~~~

* Use ``SHOW_MAX_CHILDREN`` in ``ArticleMixin`` :url-issue:`1240` (Oscar Cortez)
* Fixed wrong CSS class for collapse elements in Bootstrap 4 :url-issue:`1208` (Oscar Cortez)
* Fixed wrong version of Popper.js and update Bootstrap to v4.6.2 :url-issue:`1124` (Oscar Cortez)
* Added upper bound on dependency ``bleach>=0.5,<6`` :url-issue:`1253` (Benjamin Balder Bach)


Translation updates
~~~~~~~~~~~~~~~~~~~

- New: Portuguese ``pt_PT``: 100% translated, 100% reviewed. This comes in addition to ``pt_BR`` which was already finalized.


0.9
---

Released on 2022-06-27

Changed
~~~~~~~

* Upgrade to ``bleach>=5``, adds ``tinycss2`` dependency, drops Python 3.5 and 3.6 support :url-issue:`1183` (Benjamin Balder Bach)

Fixed
~~~~~

* Double-escaping in ``codehilite`` Markdown extension :url-issue:`945` (Benbb96 and jenda1)


0.8.2
-----

Released on 2022-05-07

Changed
~~~~~~~

* Python-Markdown updated to 3.3 :url-issue:`1180` (Benjamin Balder Bach)

Fixed
~~~~~

- Support for revision history w/ IP Address from ``HTTP_X_REAL_IP`` :url-issue:`1184` (David van Rijn)


0.8.1
-----

Released on 2022-04-25

Fixed
~~~~~

* Bootstrap pagination is updated to render as intended :url-issue:`1187` (Alexander Johan Arntzen)
* Toolchain updates: pre-commit, black, pytest, flake8, django-functests, bleach :url-issue:`1187` (Benjamin Balder Bach)


0.8
---

Released on 2022-02-14

Added
~~~~~

- Support for Django 4.0 and Python 3.10 :url-issue:`1165` (Mads Jensen)

Changed
~~~~~~~

- Bump dependency versions of sorl-thumbnail, django-nyt, django-mptt and django-functest :url-issue:`1165` (Benjamin Balder Bach)

Fixed
~~~~~

- Attachment search failing if files exceptionally missing on server :url-issue:`1162` (Benjamin Balder Bach)


0.7.10
------

Released on 2021-12-29

Fixed
~~~~~

- Missing validation for username uniqueness in in signup view :url-issue:`1152` (Benjamin Balder Bach)
- Uploading and unpacking .zip files as attachments was broken :url-issue:`1159` (kylecapricious2)


0.7.9
-----

Released on 2021-11-15.

Security fixes
~~~~~~~~~~~~~~

- XSS vulnerability: Unescaped HTML in title propagated to notification (WhiteSource Vulnerability Research Team)


0.7.8
-----

Released on 2021-10-25.

Fixed
~~~~~

- Notification menu bug after Bootstrap upgrades :url-issue:`1142` (Fred Dyc)


0.7.7
-----

Released on 2021-08-28.

Changed
~~~~~~~

- Bundled JQuery upgraded from 3.4.1 to 3.6.0 :url-issue:`1138` (Benjamin Balder Bach)

Fixed
~~~~~

- Small notification plugin registration bug introduced in 0.7.6 :url-issue:`1132` (SlyPerdix)


0.7.6
-----

Released on 2021-08-01.

Fixed
~~~~~

- Notification menu bug after Bootstrap upgrades :url-issue:`1097` (SlyPerdix)
- Compatibility with future python-markdown, use ``register`` instead of ``add`` :url-issue:`1099` (Iqbal Abdullah)


0.7.5
-----

Released on 2021-04-10.

Added
~~~~~

- Django 3.2 support :url-issue:`1121` (Benjamin Bach)


0.7.4
-----

Released on 2021-04-10.

Fixed
~~~~~

- Settings page on article broken for non-superusers :url-issue:`1058` (Benjamin Balder Bach)
- Dependency ``bleach`` is bumped to ``>=3.3.0,<3.4`` after security advisory :url-issue:`1109` (Benjamin Balder Bach)
- Font-awesome icon on external links was not showing :url-issue:`1111` (Benjamin Balder Bach)
- Red links were not correctly displaying in some cases :url-issue:`1114` (Gereon Kaiping)


Translation updates
~~~~~~~~~~~~~~~~~~~

- Chinese: 100% translated, 100% reviewed
- Czech: 100% translated
- Dutch: 100% translated, 100% reviewed
- French: Some syntax fixes, remains 100% translated
- Hungarian: 100% translated
- Korean: 100% translated, 96% reviewed
- Russian: 100% translated
- Turkish: 100% translated


0.7.3
-----

Released on 2021-01-11.

Fixed
~~~~~

- Plugin ``editsection`` failing with unexpected contents :url-issue:`1094` (Teury Diaz, Benjamin Balder Bach, OTR)


0.7.2
-----

Released on 2021-01-08.

Fixed
~~~~~

- Use ``.iter()`` instead of long deprecated and removed method ``.getiterator`` :url-issue:`1083` (Teury Diaz, Benjamin Balder Bach)


0.7.1
-----

Released on 2020-12-28.

Fixed
~~~~~

- Fixed cache key exceptions for ``SafeString` objects ``no attribute append`` :url-issue:`1072` (Gert-Jan Braas)


0.7
---

Released on 2020-10-28.

Added
~~~~~

- Django 3.1 support :url-issue:`1061` and :url-issue:`1082` (Mads Jensen, Benjamin Bach)

Fixed
~~~~~

- Do not fail prematurely during Django checks framework (rare issue) :url-issue:`1059` (Benjamin Bach)
- Cache keys failing in memcached if username contains space characters (rare) :url-issue:`1065` (Benjamin Bach)

Removed
~~~~~~~

- Django 2.1 support removed :url-issue:`1061` (Mads Jensen)

Translations
~~~~~~~~~~~~

- Japanese (ja): 100% translated
- Brazilian Portuguese (pt_BR): 100% translated


0.6
---

Released on 2020-06-03.

.. warning::

  These release contains Bootstrap v4. If you have overridden django-wiki's templates but rely on
  the distributed Bootstrap CSS, then a lot of CSS class names have changed. Please refer to
  the `Bootstrap Documentation <https://getbootstrap.com/docs/4.4/getting-started/introduction/>`__.

Added
~~~~~

- Bootstrap 4 replaces Bootstrap 3: Improved default theming. :url-issue:`1035` (slinkymanbyday, Benjamin Bach)
- Django 3.0 support :url-issue:`1019` (Benjamin Bach, slinkymanbyday)
- New plugin ``wiki.plugins.editsection`` displays an ``[edit]`` link next to section headers (Frank Loemker) :url-issue:`652`

Fixed
~~~~~

- Python 3.7 issue with notifications plugin main view ``/_plugin/notifications/`` :url-issue:`1000` (Mads Jensen)
- Broken Delete and Deleted pages :url-issue:`976` (Benjamin Bach)
- Can't delete article with ``USE_THOUSAND_SEPARATOR = True`` :url-issue:`1014` (tim3towers)
- Deleting images fails :url-issue:'936' (Gert-Jan Braas, Steckelfisch)

Changed
~~~~~~~

- Use SASS instead of LESS for Stylesheets. The compiler in ``Makefile`` is ``lessc``. :url-issue:`1035` (Benjamin Bach)
- Removed ``src/wiki/static/wiki/css/wiki-bootstrap.css`` - Only distribute a minified CSS version. :url-issue:`1035` (Benjamin Bach)
- Test coverage upped from 75 to 80+% :url-issue:`976` (Mads Jensen, Benjamin Bach)
- PDF attachment Content-Disposition header changed to ``inline`` for browser previewing :url-issue:`1010` (nicolazilio)
- PyTest upgraded to latest 5.3
- django-mptt updated from 0.9 to 0.11.0 :url-issue:`1019` (Benjamin Bach, slinkymanbyday)
- sorl-thumbnail bumped to 12.6.2 :url-issue:`1019` (Benjamin Bach, slinkymanbyday)
- Upgrade bleach from 2.1 to 3.1 :url-issue:`1020` (slinkymanbyday)
- Python-Markdown 3.2 compatibility (Benjamin Bach)

Removed
~~~~~~~

- Python 3.4 support more or less definitively removed (no longer supported by test suite PyTest)
- Removed unmaintained plugin ``wiki.plugins.haystack``

Translations
~~~~~~~~~~~~

- Dutch translation 100% completed :url-issue:`1037` (Gert-Jan Braas)
- Polish 100% completed

0.5
---

**Compatibility note, 2020-02-18**: Django 3.0 support was scheduled but never completed, as dependencies lacked the support. It was completed in 0.6.

Changed
~~~~~~~

- Update to Markdown >= 3.1 :url-issue:`920` (Don Bowman, Benjamin Bach)
- Several code-cleanups, test improvements and test

Added
~~~~~

- Django 2.2

Removed
~~~~~~~

- Django 1.11 support

Translations
~~~~~~~~~~~~

We need help to complete translations. It's done easily by creating a profile and joining
`the django-wiki project on Transifex <https://www.transifex.com/django-wiki/django-wiki/>`__. You are also
encouraged to create new languages if you would like to translate to a language that doesn't yet exist.


0.4.5
-----

Fixed
~~~~~

- Django admin error when uploading images: Column 'revision_number' cannot be null :url-issue:`950` (Benjamin Bach)

Translations
~~~~~~~~~~~~

- Added: Romanian ``ro``


0.4.4
-----

Fixed
~~~~~

- Projects fail to load with custom ``User`` models without a ``username`` field :url-issue:`865` (trevorpeacock)
- Use ``User.get_username()`` for article cache instead of ``User.__str__`` :url-issue:`931` (Ole Anders Stokker)


0.4.3
-----

Discarded release due to git errors (the actual fixes were not merged in).

- Automated language updates from Transifex


0.4.2
-----

Fixed
~~~~~

- Using customized ``MESSAGE_TAGS`` setting caused ``KEY_ERROR`` :url-issue:`922` (Benjamin Bach)


0.4.1
-----

Security
~~~~~~~~

- jQuery upgrade from 1.12.4 to 3.3.1. jQuery UI also upgraded (for dynamic resizing of modals) :url-issue:`882` (Benjamin Bach)

0.4
---

Added
~~~~~

- Django 2.0 and 2.1 support :url-issue:`755` (Raffaele Salmaso & Mads Jensen)
- Python 3.7 support
- Added ``wiki.sites.WikiSite`` for easy customization :url-issue:`827`
- Automatic link highlighting of URLs handles lots of new patterns :url-issue:`816` (Branko Majic)
- Red links: Internal links turn red and link to Create Page (Mathias Rav)  :url-issue:`889`

Translations
~~~~~~~~~~~~

- Merged ``pt`` and ``pt_PT``, then deleted ``pt`` and linked it to ``pt_PT`` :url-issue:`858`
- Linked ``zh_Hans`` to ``zh_CN`` :url-issue:`711`

Complete / almost complete:

- Chinese (China)	``zh_CN``	100.00%
- Danish	``da``	100.00%
- Dutch	``nl``	94.32%
- French	``fr``	97.95%
- German	``de``	95.00%
- Korean (Korea)	``ko_KR``	95.00%
- Polish (Poland)	``pl_PL``	98.18%
- Portuguese (Brazil)	``pt_BR``	95.00%
- Russian	``ru``	99.55%
- Slovak	``sk``	94.77%
- Spanish	``es``	94.77%

Well under way, `need support <https://www.transifex.com/django-wiki/django-wiki/languages/>`__:

- Chinese (Taiwan)	``zh_TW``	34.55%
- Czech	``cs``	35.45%
- Finnish	``fi``	81.14%
- Italian	``it``	47.05%
- Japanese	``ja``	79.77%
- Norwegian Bokmål (Norway)	``nb_NO``	34.77%
- Portuguese (Portugal)	``pt_PT``	79.32%
- Turkish (Turkey)	``tr_TR``	30.68%

Changed
~~~~~~~

- Dependency for escaping HTML and safeguarding against injections ``bleach`` upgraded ``>=2.1,<2.2`` (last-partizan) :url-issue:`702`
- Use full path names for ``MARKDOWN_KWARGS['extensions']`` as short names support wil be removed in ``Markdown 2.7`` :url-issue:`823`
- Support for ``include('wiki.urls')`` for urls instantiation :url-issue:`827`
- Use Django's 'checks.py' pattern to test configuration (Raffaele Salmaso & Mads Jensen) :url-issue:`830` :url-issue:`807`
- Test coverage added: Images plugin + Account handling (Mads Jensen) :url-issue:`804`
- Last couple of non-CBVs (Class Based Views) refactored to CBV (Raffaele Salmaso & Mads Jensen) :url-issue:`788` :url-issue:`819` :url-issue:`808`
- Big cleanup: Deprecating lots of Python 2.7 specific code (Mads Jensen & Raffaele Salmaso) `See: >30 PRs <https://github.com/django-wiki/django-wiki/pulls?q=is%3Apr+is%3Aclosed+label%3Aclean-up>`__
- Search term highligting tweaked, first match is now highlighted instead of last (Mathias Rav)  :url-issue:`901`
- Markdown parsing for ``[image]``, ``[article_list]`` and macros rewritten and improved to allow escaping (Mathias Rav) :url-issue:`896`

Fixed
~~~~~

- Use ``user.is_authenticated/is_anonymous`` as a boolean :url-issue:`790` (Raffaele Salmaso)
- Use ``simple_tag`` for assignment tag :url-issue:`791` (Raffaele Salmaso)
- Direct invocation of ``pytest`` fixed (removing ``runtests.py``) :url-issue:`781` (Branko Majic)
- Line breaks in help texts for macros :url-issue:`851` (Mathias Dannesbo)
- Table of contents now has a header by default, and several built-in django-wiki extensions can be configured using ``WIKI_MARKDOWN_KWARGS`` :url-issue:`881` (Mathias Rav)
- S3 Storage engine image deletion bug :url-issue:`907` (Andrea Maschio & Benjamin Bach)
- Back link on "permission denied" page should point to parent article on read errors :url-issue:`915` (Benjamin Bach & Christian Duvholt)

Deprecated/Removed
~~~~~~~~~~~~~~~~~~

- Django < 1.11 support is dropped :url-issue:`779`
- Python < 3.3 support is dropped :url-issue:`779` and :url-issue:`792`
- Deprecate ``wiki.urls.get_pattern`` and ``URL_CONFIG_CLASS`` setting :url-issue:`799`
- Removed ``SEARCH_VIEW`` setting, replaced by ``WikiSite`` override :url-issue:`837`


0.3.1
-----

- Fix error messages of missing migrations due to inconsistent change of ``on_delete`` on some model fields :url-issue:`776`


0.3
---

Translation updates from Transifex
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- Languages that `need support <https://www.transifex.com/django-wiki/django-wiki/languages/>`__:

  * Dutch 88%
  * Finnish 85%
  * Japanese 80%
  * Chinese (Taiwan) 36%
  * Norwegian 36%
  * Turkish 30%
  * Czech 13%
  * Italian 8%

- >90% completed: Chinese, French, German, Russian, Spanish, Danish, Korean, Polish, Portuguese (Brazilian), Slovak, Spanish

Added
~~~~~

- Search choice between either current or global tree (Christian Duvholt) :url-issue:`580` :url-issue:`731`
- New bootstrapped image insert dialog (Frank Loemker) :url-issue:`628`
- Allow the HTML tag ``<hr>`` (Frank Loemker) :url-issue:`629`
- Global History overview of page revisions (Frank Loemker and Maximilien Cuony) :url-issue:`627`
- Move article support with redirects (Frank Loemker) :url-issue:`640`
- Django 1.11 compatibility (Luke Plant) :url-issue:`634`
- Crop paginator window when there are >9 pages in a list (Frank Loemker) :url-issue:`646`
- Extended syntax for attachment macro: ``[attachment:id title:"text" size]`` (Frank Loemker) :url-issue:`678`
- Add Sphinx documentation for plugin settings (Frank Loemker) :url-issue:`681`
- Show "log out" in menu when account handling is disabled (jenda1) :url-issue:`691`
- Markdown tag with wiki paths now support fragments like
  ``[Click Here](wiki:/path#header)`` (Frank Loemker) :url-issue:`701`

Changed
~~~~~~~

- Test refactor: Use django-functest and separate WebTest from Selenium (Luke Plant) :url-issue:`634`
- Repo refactor: Moved ``wiki`` package to ``src/`` folder and test code to ``tests/`` :url-issue:`631`
- Render django.contrib.messages with template tag and inclusion template: Configurable and bootstrap 3 compatible (Benjamin Bach and Frank Loemker) :url-issue:`654`
- Don't hardcode redirect url in account update view (Benjamin Bach) :url-issue:`650`
- Python 3.6 support added to test matrix (Benjamin Bach) :url-issue:`664`
- Keep CSS global namespace clean, refactor CSS rule ``label`` -> ``.wiki-label label`` (Christian Duvholt) :url-issue:`679`
- Plugins can whitelist HTML tags and attributes (jenda1) :url-issue:`700`
- Optimizations to fundamental permission lookup managers (Christian Duvholt) :url-issue:`714`
- Code quality upgrade, remove obsolete code, linting and tidying up (Mads Jensen) :url-issue:`797`, :url-issue:`705`, :url-issue:`707`, :url-issue:`716`, :url-issue:`717`, :url-issue:`718`, :url-issue:`719`, :url-issue:`720`, :url-issue:`721`, :url-issue:`722`, :url-issue:`724`, :url-issue:`725`, :url-issue:`726`, :url-issue:`727`, :url-issue:`728`, :url-issue:`730`, :url-issue:`732`, :url-issue:`733`, :url-issue:`735`, :url-issue:`736`, :url-issue:`737`, :url-issue:`738`, :url-issue:`741`, :url-issue:`743`, :url-issue:`743`, :url-issue:`756`, :url-issue:`757`
- Added ``AppConfig`` class for all plugins (Raffaele Salmaso) :url-issue:`758`
- Explicit ``on_delete`` for all ``ForeignKey`` fields (Raffaele Salmaso) :url-issue:`759`
- Django 2.0 preparation: ``atomic=False`` for 3 migrations that rename tables/fields (Raffaele Salmaso) :url-issue:`760`
- Set dependency ``django-nyt<1.1`` to avoid future breakage (Benjamin Bach) :url-issue:`761`


Fixed
~~~~~

- Removed exception catch all in ``URLPath.delete_subtree`` which silenced errors while delete articles with descendents
- Fix article settings page in Django 1.11 (Frank Loemker) :url-issue:`682`
- Fix upstream MPTT breaking deletion of articles from django-admin (Frank Loemker) :url-issue:`683`
- Wrong HTML attribute 'type' on search result page (Geoff Clapp) :url-issue:`698`
- Fix restoring of attachments and other RevisionPlugin types after deletion (Frank Loemker) :url-issue:`672`
- Allowing ``<sup>`` because of footnotes (Frank Loemker) :url-issue:`750`
- Hunted down unclosed HTML tags :url-issue:`750` (Mads Jensen) :url-issue:`741`


0.2.5
-----

- Set dependency ``django-nyt<1.1`` to avoid future breakage (Benjamin Bach) :url-issue:`761`


0.2.4
-----

- Hot-fix because of missing woff2 files :url-issue:`625`


0.2.3
-----

- Pulled Transifex translations and pushed source translations.
- Fix support for Py2 unicode in code blocks (Benjamin Bach) :url-issue:`607`
- Support for Github style fenced codeblocks (Benjamin Bach) :url-issue:`618`
- Cached articles showing up in wrong language (Benjamin Bach) :url-issue:`592`
- Upgraded Bootstrap from 3.3.1 to 3.3.7 (Benjamin Bach) :url-issue:`620`
- Upgraded bundled jQuery to 1.12.4 (Benjamin Bach) :url-issue:`620`
- Setting ``WIKI_MARKDOWN_HTML_STYLES`` for allowing ``style='..'`` in user code (Benjamin Bach) :url-issue:`603`
- Strip Markdown code in search result snippets (Benjamin Bach) :url-issue:`42`


0.2.2
-----

- Remove ``wiki.decorators.json_view``, fixes server errors when resolving 404 links :url-issue:`604`
- Replace usage of ``render_to_response()`` with ``render()`` :url-issue:`606`
- Fix memory leak :url-issue:`609` and :url-issue:`611` (obtroston)
- Scroll bars and display area fixed for code blocks :url-issue:`601` and :url-issue:`608` (Branko Majic)
- Option ``WIKI_MARKDOWN_SANITIZE_HTML`` skips Bleach (warning: Don't use for untrusted code) :url-issue:`610` (Michal Hozza)
- Allow the HTML tag ``<br>``. :url-issue:`613` (Frank Loemker)
- Add thumbnail size directive (example: ``[image:123 size:large]``). :url-issue:`612` (Frank Loemker and @inflrscns)
- Fix error with absolute paths in wiki links (example: ``[Sub-root](wiki:/sub-root)``) :url-issue:`616` (Benoit C. Sirois)
- Require ``Django<1.11`` :url-issue:`616` (Benoit C. Sirois)


0.2.1
-----

- Lowercase slugs when creating new pages with ``[[Like This]]`` :url-issue:`595` (Eric Clack)
- Fix issues related to Bleach before Markdown processing esp. pertaining ``>`` characters. :url-issue:`596`
- Remove ``wiki.plugins.mediawikiimport`` :url-issue:`597`
- Pretty up the highligted code's line enumeration :url-issue:`598`
- Customize codehilite in order to wrap highlighted code with scrollbars :url-issue:`598`


0.2
---

- Translation updates from Transifex

  * Danish translation from 39% to 100% (Bo Holm-Rasmussen)
  * Updated languages since 0.1: Chinese, French, German, German, Russian, Spanish

- Added Django 1.10 support :url-issue:`563`
- Security: Do not depend on markdown ``safe_mode``, instead use ``bleach``.
- Fix duplicate search results when logged in :url-issue:`582` (duvholt)
- Do not allow slugs only consisting of numbers :url-issue:`558`
- Copy in urlify.js and fix auto-population of slug field in Django 1.9+ :url-issue:`554`
- Fix memory leak in markdown extensions setting :url-issue:`564`
- Updated translations - Languages > 90% completed: Chinese (China), Portuguese (Brazil), Korean (Korea), French, Slovak, Spanish, Dutch, German, Russian, Finnish.
- Taiwanese Chinese added (39% completed)
- Cleanup documentation structure :url-issue:`575`

HTML contents
~~~~~~~~~~~~~

`Bleach <https://github.com/mozilla/bleach>`_ is now used to sanitize HTML
before invoking Markdown.

HTML escaping is done before Markdown parsing happens. In future Markdown
versions, HTML escaping is no longer done, and ``safe_mode`` is removed. We have
already removed ``safe_mode`` from the default ``WIKI_MARKDOWN_KWARGS`` setting,
however if you have configured this yourself, you are advised to remove
``safe_mode``.

Allowed tags are from Bleach's default settings: ``a``, ``abbr``, ``acronym``,
``b``, ``blockquote``, ``code``, ``em``, ``i``, ``li``, ``ol``, ``strong``,
``ul``.

Please use new setting ``WIKI_MARKDOWN_HTML_WHITELIST`` and set a list of
allowed tags to customize behavior.


Python and Django support
~~~~~~~~~~~~~~~~~~~~~~~~~

Support has been removed for:

- Python 2.6
- Django < 1.8
- South

0.1.2
-----

- Remove unwanted items from default menu when ``WIKI_ACCOUNT_HANDLING = False``. :url-issue:`545`
- Fix broken soft-deletion and restoring of images, and "set revision" functionality :url-issue:`533`
- Added responsiveness to tables by use of Bootstrap table-responsive class :url-issue:`552`


0.1.1
-----

- Several languages updated from Transifex

  * Slovak added **Thanks M Hozza**
  * Portuguese also added, but as copy of PT-BR (make changes as desired in Transifex)

- Brand new Account Settings page (email / password) **Thanks inflrscns**
- Testproject turned into Django 1.9 layout
- Replace context-processor dependent use of ``{{ STATIC_URL }}`` with ``{% static %}``
- Bugfix for ``pip install wiki`` in an empty (no Django installed) virtualenv
- Precommit hooks added in repository
- Import statements sorted and codebase re-pep8'thed
- Log in page is now called "Log in" in ``<title>`` tag - **Thanks Eugene Obukhov**


0.1
---

.. warning::
   If you are upgrading from a previous release, please ensure that you
   pass through the 0.0.24 release because it contains the final migrations
   necessary before entering the django-wiki 0.1+ migration tree.

   If you are using django 1.7+ and have an old installation of django-wiki
   (which should be impossible since it wouldn't run) please downgrade to 1.6
   as follows:

   ::

       $ pip install wiki\<0.1 --upgrade  # Latest 0.0.24 release
       $ pip install django\<1.7  # Downgrade django if necessary
       $ python manage.py migrate  # Run 0.0.24 migrations
       $ pip install wiki\<0.2 --upgrade  # Upgrade to latest 0.1 series
       $ python manage.py migrate --delete-ghost-migrations  # Run migrations again,
                                                             # removing the (ghost)
                                                             # migrations from previous
                                                             # release
       $ # Feel free to upgrade Django again


**Supported**

- Python 2.7, 3.3, 3.4, 3.5 (3.2 is not supported)
- Django 1.5, 1.6, 1.7, 1.8, 1.9
- Django < 1.7 still needs South, and migration trees are kept until next major
  release.


Breaking changes
~~~~~~~~~~~~~~~~

**wiki.VERSION as tuple**

We want to follow Django's way of enumerating versions. If you want the old
string version, use ``wiki.__version__``.

**Plugin API**

Since Django 1.8 has started making warnings about `patterns` being deprecated, we've decided
to stop using them by default. Thus, as with the future Django 2.0, we will use lists of `url`
objects to store the urlconf of plugins. All the bundled plugins have been updated to reflect
the change.

**Django-mptt**

We now depend on django-mptt 0.7.2+ for Django 1.8 compatibility.


0.0.24
------

This release is a transitional release for anyone still using an older version
of django-wiki. The code base has been heavily refactored and this is hopefully
the final release.

.. warning::
   0.0.24 is mainly a transitional release, but new features and bug fixes are
   included, too.

**Compatibility**

- Django 1.5, 1.6 (That means Django 1.7 is **not** yet fully supported)
- South 1.0+ (if you are on an older South, you **need** to upgrade)
- Python 2.6, 2.7, 3.3, 3.4


Upgrading
~~~~~~~~~

Firstly, upgrade django-wiki through familiar steps with pip

::

    $ pip install wiki --upgrade

During the upgrade, notice that `django-nyt`_ is installed. This replaces the
previously bundled django_notify and you need to make a few changes in
your settings and urls.

.. _django-nyt: https://github.com/benjaoming/django-nyt

In ``settings.INSTALLED_APPS``, replace `"django_notify"` with `"django_nyt"`.
Then open up your project's urlconf and make sure you have something
that looks like the following:

::

    from wiki.urls import get_pattern as get_wiki_pattern
    from django_nyt.urls import get_pattern as get_nyt_pattern
    urlpatterns += patterns('',
        (r'^notifications/', get_nyt_pattern()),
        (r'', get_wiki_pattern())
    )

Notice that we are importing `from django_nyt.urls` and no longer
`django_notify` and that the function is renamed to `get_nyt_pattern`.

After making these changes, you should run migrations.

::

    $ python manage.py migrate


**Notifications fixed**

In past history, django-wiki has shipped with `a very weird migration`_. It
caused for the notifications plugin's table of article subscriptions to be removed.
This is fixed in the new migrations and the table should be `safely restored`_ in
case it was missing.

.. _a very weird migration: https://github.com/django-wiki/django-wiki/commit/88847096354121c23d8f10463201da5e0ebd7148
.. _safely restored: https://github.com/django-wiki/django-wiki/blob/releases/0.0.24/wiki/plugins/notifications/south_migrations/0003_conditionally_restore_articlesubscription.py

However, you may want to bootstrap subscription notifications in case you have run
into this failed migration. You can ensure that all owners and editors of articles
receive notifications using the following management command:

    python manage.py wiki_notifications_create_defaults


Troubleshooting
~~~~~~~~~~~~~~~


If you have been running from the git master branch, you may experience
problems and need to re-run the migrations entirely.

::

    python manage.py migrate notifications zero --delete-ghost-migrations
    python manage.py migrate notifications

If you get `DatabaseError: no such table: notifications_articlesubscription`,
you have been running django-wiki version with differently named tables.
Don't worry, just fake the backwards migration:

::

    python manage.py migrate notifications zero --fake

If you get ``relation "notifications_articlesubscription" already exists`` you
may need to do a manual ``DROP TABLE notifications_articlesubscription;`` using
your DB shell (after backing up this data).

After this, you can recreate your notifications with the former section's
instructions.



News archive
------------

April 15, 2017
~~~~~~~~~~~~~~

0.2.3 released: `Release notes <http://django-wiki.readthedocs.io/en/main/release_notes.html#django-wiki-0-2-3>`__

0.2.2 released: `Release notes <http://django-wiki.readthedocs.io/en/main/release_notes.html#django-wiki-0-2-2>`__


February 27, 2017
~~~~~~~~~~~~~~~~~

0.2.1 released: `Release notes <http://django-wiki.readthedocs.io/en/main/release_notes.html#django-wiki-0-2-1>`__


December 27, 2016
~~~~~~~~~~~~~~~~~

0.2 final released: `Release notes <http://django-wiki.readthedocs.io/en/0.2/release_notes.html>`__


June 19, 2016
~~~~~~~~~~~~~

0.1.2 released: `Release notes <http://django-wiki.readthedocs.io/en/latest/release_notes.html#django-wiki-0-1-2>`__

May 6, 2016
~~~~~~~~~~~

0.1.1 released: `Release notes <http://django-wiki.readthedocs.io/en/latest/release_notes.html#django-wiki-0-1-1>`__


January 25, 2016
~~~~~~~~~~~~~~~~

0.1 final released


December 26th, 2015
~~~~~~~~~~~~~~~~~~~

A new release 0.0.24.4 is out and has fixes for the Django ``loaddata`` management command such that you can create dumps and restore the dump. Notice, though, that ``loaddata`` only works for Django 1.7+.

Django 1.9 support is available in the current master, please help get a 0.1 released by giving feed back in the last remaining issues:

https://github.com/django-wiki/django-wiki/milestones/0.1


November 16th, 2015
~~~~~~~~~~~~~~~~~~~

Django 1.8 support is very ready and 0.1 is right on the doorstep now.


January 26th, 2015
~~~~~~~~~~~~~~~~~~

After too long, the new release is out.

The wait was mainly due to all the confusing changes by adding support
of Python 3 and readying the migrations for Django 1.7. But there's
actually new features, too.

-  Bootstrap 3.3.1 and Font Awesome 4 (Christian Duvholt)
-  ``django_nyt`` instead of builtin ``django_notify`` (Benjamin Bach,
   Maximilien Cuony)
-  ``tox`` for testing (Luke Plant)
-  Appropriate use of gettext\_lazy (Jaakko Luttinen)
-  Fixed support of custom username fields (Jan De Bleser)
-  Several fixes to the attachment plugin (Christian Duvholt)
-  Errors on notifications settings tab (Benjamin Richter)
-  Chinese translations (Ronald Bai)
-  Finish translations (Jaakko Luttinen)
-  Compatibility with custom user model in article settings (Andy Fang)
-  Fixed bug when ``[attachment:XX]`` present multiple times on same
   line (Maximilien Cuony)
-  Simple mediawiki import management command (Maximilien Cuony)
-  Python 3 and Django 1.6 compatibility (Russell-Jones, Antonin
   Lenfant, Luke Plant, Lubimov Igor, Benjamin Bach)
-  (and more, forgiveness asked if anyone feels left out)
