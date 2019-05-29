Simple Sphinx
===============

Sphinx generates project documentation, which can be hosted easily at
`readthedocs <https://readthedocs.org/>`_.

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

4. From your `readthedocs dashboard <https://readthedocs.org/dashboard/>`_, import
your github project repository.

5. You can soon access the documentation online, either from your
dashboard or the provided URL.

*(Optional)* Setup RTD Theme
-----------------------------
`It looks like this 🌈. <https://bootstrap-datepicker.readthedocs.io/en/latest/>`_

::

    $ pip install sphinx_rtd_theme

In your conf.py file, set ``html_theme``::

    html_theme = "sphinx_rtd_theme"


Develop
---------

Documentation is written in restructuredText (`quickstart <http://docutils.sourceforge.net/docs/user/rst/quickstart.html>`_).

Only .rst files need to be created and edited.

Use `vscode <https://code.visualstudio.com/>`_ and install the
`reStructuredText extension <https://marketplace.visualstudio.com/items?itemName=lextudio.restructuredtext>`_.
The extension allows you to preview your documentation with
*Open Locked Preview to the Side* (find it with *Ctrl/Cmd+Shift+P*.)

To view the HTML locally, within your ``docs`` folder::

    $ make html
    $ open _build/html/index.html
