Condition syntax
################

Trigger conditions can be described by following list of operators,
values and functions.

Operators
=========

Logical
^^^^^^^

.. list-table::
   :header-rows: 1

   *  - Operator
      - Description
   *  - ``or``, ``||``
      - .. code::

         TRUE if either Boolean expression is TRUE.

         Example:

            [Comment.CommentType] = 'Public' or [Ticket.Created] < '#01/01/2015#'

   *  - ``and``, ``&&``
      - .. code::

         TRUE if both Boolean expression is TRUE.

         Example:

            [Ticket.AssignedTo] = '' and [Ticket.AssignedTo] = [Editor]

The ``and`` operator has more priority than the ``or``.

Relational
^^^^^^^^^^

-  ``=``, ``==``, ``!=``, ``<>``
-  ``<``, ``<=``, ``>``, ``>=``

.. code::

    1 < 2

Additive
^^^^^^^^

-  ``+``, ``-``

.. code::

    1 + 2 - 5

Multiplicative
^^^^^^^^^^^^^^

-  ``*``, ``/``, ``%``

.. code::

    5 * 5


Unary
^^^^^

-  ``!``, ``not``, ``-``, ``~`` (bitwise not) 

.. code::

    not true

Primary
^^^^^^^

-  ``(``, ``)``
-  values

.. code::

    (2 + 3) * 4

Values
======

References
^^^^^^^^^^

.. list-table::
   :header-rows: 1

   *  - Operator
      - Description
   *  - ``[LastTicketVersion]``
      - .. code::

         Return ticket item before changes.

         Example:

             ([LastTicketVersion.Status.Title] <> [Ticket.Status.Title]) and ([Ticket.Status.Title] = 'Solved')

Integers
^^^^^^^^

They are represented using numbers. 

.. code::

    123456

Floating point numbers
^^^^^^^^^^^^^^^^^^^^^^

Use the dot to define the decimal part. 

.. code::

    123.456
    .123

They are evaluated as \ **Decimal**\ .


Dates and Times
^^^^^^^^^^^^^^^

Must be enclosed between sharps. 

.. code::

    #2008/01/31# // for en-US culture

Booleans
^^^^^^^^

Booleans can be either ``true``  or ``false``.

.. code::

    true

Strings
^^^^^^^

Any character between single quotes ``'`` are evaluated
as \ **String**\ . 

.. code::

    'hello'

You can escape special characters
using \ **\\\\**\ , \ **\\'**\ , \ **\\n**\ , \ **\\r**\ , \ **\\t**\ .

Function
^^^^^^^^

A function is made of a name followed by braces, containing optionally
any value as arguments.

.. code::

    Abs(1), doSomehting(1, 'dummy')

Parameters
^^^^^^^^^^

A parameter as a name, and can be optionnally contained inside brackets.

.. code::

    2 + x, 2 + [x]

Functions
=========

.. list-table::
   :header-rows: 1

   *  - Name
      - Description
      - Usage
      - Result
   *  - **Abs**
      - Returns the absolute value of a specified number.
      - ``Abs(-1)``
      - ``1M``
   *  - **Ceiling**
      - Returns the smallest integer greater than or equal to the specified number.
      - ``Ceiling(1.5)``
      - ``2d``
   *  - **Floor**
      - Returns the largest integer less than or equal to the specified number.
      - ``Floor(1.5)``
      - ``1d``
   *  - **Max**
      - Returns the larger of two specified numbers.
      - ``Max(1, 2)``
      - ``2``
   *  - **Min**
      - Returns the smaller of two numbers.
      - ``Min(1, 2)``
      - ``1``
   *  - **Round**
      - Rounds a value to the nearest integer or specified a number of decimal places. The mid number behavior can be changed by using EvaluateOption.RoundAwayFromZero during construction of the Expression object.
      - ``Round(3.222, 2)``
      - ``3.22d``
   *  - **Today()**
      - Returns the current system date.
      - ``Today()``
      - ``#01/02/2017#``
   *  - **Now()**
      - Returns the current system date and time.
      - ``Now()``
      - ``#01/02/2017 13:47#``
   *  - **Date()**
      - Returns the date part of a particluar datetime value.
      - ``Date([Ticket.Created])``
      - ``#01/02/2017#``
   *  - **AddMinutes()**
      - Adds the specified number of minutes to the specified date parameter.
      - ``AddMinutes(#01/02/2017 13:45#, 2)``
      - ``#01/02/2017 13:47#``
   *  - **AddHours()**
      - Adds the specified number of hours to the specified date parameter.
      - ``AddHours(#01/02/2017 13:45#, 2)``
      - ``#01/02/2017 15:45#``
   *  - **AddDays()**
      - Adds the specified number of days to the specified date parameter.
      - ``AddDays(#01/04/2017 12:00#, 2)``
      - ``#03/04/2017 12:00#``
   *  - **AddMonths()**
      - Adds the specified number of months to the specified date parameter.
      - ``AddMonths(#01/04/2017 12:00#, 2)``
      - ``#01/06/2017 12:00#``
   *  - **AddYears()**
      - Adds the specified number of years to the specified date parameter.
      - ``AddYears(#01/02/2017 12:00#, 2)``
      - ``#01/02/2019 12:00#``


It also includes other general purpose ones.

.. list-table::
   :header-rows: 1

   *  - Name
      - Description
      - Usage
      - Result
   *  - **in**
      - Returns whether an element is in a set of values.
      - ``in(1 + 1, 1, 2, 3)``
      - ``true``
   *  - **if**
      - Returns a value based on a condition.
      - ``if(3 % 2 = 1, 'value is true', 'value is false')``
      - ``value is true``
   *  - **contains**
      - Returns true if the first string contains the second.
      - ``contains('1234', '23')``
      - ``true``
   *  - **match**
      - Indicates whether the specified regular expression (second argument) finds a match in the specified input string (first argument). This pattern can contain inline options to modify behavior of the regular expression. Such options have to be placed in the beginning of the expression inside brackets with question mark: ``(?YOUR_OPTIONS)``. For example options ``(?mi)`` will allow to process multi line text with case insensitivity. Example of regular expression with options:``(?mi)(?[^>]*@[^<]*)``.
        List of available options:
        ::

          x - allow whitespace and comments 
          s - single line mode
          m - multi line mode 
          i - case insensitivity 
          n - only allow explicit capture
        You can find additional information about inline options in this `MSDN article <http://msdn.microsoft.com/en-us/library/yd1hzczs%28v=vs.110%29.aspx>`_.
      - ``match('1298-673-4192', '^[a-zA-Z0-9]\d{2}[a-zA-Z0-9](-\d{3}){2}[A-Za-z0-9]$')``
      - ``true``