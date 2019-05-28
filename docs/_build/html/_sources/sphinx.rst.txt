Simple Sphinx
===============

Your project should be in a `github <https://github.com/>`_ repository. Then,
sign up for a `readthedocs account <https://readthedocs.org/accounts/signup/>`_ with
your github account.


Setup new project
-------------------

1. Install sphinx with pip::

    $ pip install sphinx

2. As best practice, use a separate ``docs`` folder. From your project folder::

    $ mkdir docs
    $ cd docs

3. Use the sphinx quickstart and follow the prompts::

    $ sphinx-quickstart

4. Run ``make html`` to create the html file::

    $ make html

5. Open the html file to view it::

    $ open _build/html/index.html


*(Optional)* Use RTD Theme
--------------------------
`It looks like this.🌈 <https://bootstrap-datepicker.readthedocs.io/en/latest/>`_

::

    $ pip install sphinx_rtd_theme

In your conf.py file::

    html_theme = "sphinx_rtd_theme"

Interesting Section
-------------------

Here's the awesome content!


Awesome foods:

* Bananas
* Strawberries


Great programming languages:

#. python
#. javascript

I like **jam**. Like, I like it *a lot*. Almost as much as i love ``git push``.
This is `my favorite song <https://www.animelyrics.com/anime/kiminonawa/nandemonaiya.htm>`_.

This is a simple example::

    import math
    print 'import done'


.. image:: https://picsum.photos/200/300
    :width: 200px
    :align: center
    :height: 100px
    :alt: alternate text


.. seealso:: This is a simple **seealso** note.

.. note::  This is a **note** box.

.. warning:: note the space between the directive and the text

:download:`download samplet.py <sample.py>`

.. math::

    n_{\mathrm{offset}} = \sum_{k=0}^{N-1} s_k n_k

Some text that requires a footnote [#f1]_ .

.. rubric:: Footnotes

.. [#f1] Text of the first footnote.

