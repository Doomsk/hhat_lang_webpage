====
Installation
====

To install the **H-hat interpreter**, it is recommended to follow the steps:

*  Install **Python 3.10+**.
* Set up a virtual environment, such as `anaconda <https://www.anaconda.com/products/individual>`_ or `venv <https://docs.python.org/3/library/venv.html>`_.
* Install the package, via `PYPI <https://pypi.org/>`_ (instructions `below <PYPI installation_>`_)) or in [development mode](#development-mode).

Setting up a virtual environment
--------------------------------

In case you don't know how to set up a virtual environment, see the examples below (choose only one):

Using conda
-----------

* Install `anaconda <https://www.anaconda.com/products/individual>`_.
* Create an environment for `h-hat` and activate it: `conda activate <name_of_the_env>`

Using venv
----

* Create a venv: `python3.10 -m venv .venv` (the venv will be located in the folder `.venv` inside the hhat_lang root folder)
* Deactivate any other environment you might have active, i.e. conda: `conda deactivate`, until you have no environment
* Activate our new venv through: `source .venv/bin/activate`


PYPI installation
----

After setting up your virtual environment, simply use:

.. code-block:: shell-session

    python3 -m pip install hhat-lang


Development mode
----

In the root folder, run:

.. code-block:: shell-session

    python3 -m pip install -e .


Executing Code
-----

After proceeding on your preferred installation method, it's time to run some code. Just type `hhat` in the terminal followed by the file containing your code (`.hat` extension).
