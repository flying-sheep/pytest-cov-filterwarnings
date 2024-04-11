pytest-cov-filterwarnings
=========================

Reproducer for https://github.com/pytest-dev/pytest-cov/issues/627

To reproduce:

.. code-block:: python

   hatch run pytest --cov

Which will output this coverage report, showing missing lines in the package.
This is caused by pytest importing the warning class before `pytest-cov` is initialized.

.. code-block::

   ---------- coverage: platform darwin, python 3.11.7-final-0 ----------
   Name                               Stmts   Miss  Cover
   ------------------------------------------------------
   src/pytest_cov_filterwarnings.py       4      3    25%
   tests/test_basic.py                    3      0   100%
   ------------------------------------------------------
   TOTAL                                  7      3    57%
