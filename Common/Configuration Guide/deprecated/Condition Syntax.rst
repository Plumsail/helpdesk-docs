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

            [CommentType] = 'Public' or [Created] < '#01/01/2015#'

   *  - ``and``, ``&&``
      - .. code::

         TRUE if both Boolean expression is TRUE.

         Example:

            [AssignedTo] = '' and [AssignedTo] = [Editor]

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

Bitwise
^^^^^^^

-  ``&`` (bitwise and), ``|`` (bitwise or), ``^`` (bitwise xor), ``<<`` (left shift), ``>>`` (right shift)

.. code::

    1 >> 5

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
   *  - ``[Prev]``
      - .. code::

         Return ticket item before changes.

         Example:

            ([Prev::Status] <> [Status]) and ([Status] == 'Solved')

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

Scientific notation
^^^^^^^^^^^^^^^^^^^

You can use the ``e``  to define power of ten (10^).

.. code::

    1.22e1
    1e2
    1e+2
    1e-2
    .1e-2
    1e10

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
   *  - **Acos**
      - Returns the angle whose cosine is the specified number.
      - ``Acos(1)``
      - ``0d``
   *  - **Asin**
      - Returns the angle whose sine is the specified number.
      - ``Asin(0)``
      - ``0d``
   *  - **Atan**
      - Returns the angle whose tangent is the specified number.
      - ``Atan(0)``
      - ``0d``
   *  - **Ceiling**
      - Returns the smallest integer greater than or equal to the specified number.
      - ``Ceiling(1.5)``
      - ``2d``
   *  - **Cos**
      - Returns the cosine of the specified angle.
      - ``Cos(0)``
      - ``1d``
   *  - **Exp**
      - Returns e raised to the specified power.
      - ``Exp(0)``
      - ``1d``
   *  - **Floor**
      - Returns the largest integer less than or equal to the specified number.
      - ``Floor(1.5)``
      - ``1d``
   *  - **IEEERemainder**
      - Returns the remainder resulting from the division of a specified number by another specified number.
      - ``IEEERemainder(3, 2)``
      - ``-1d``
   *  - **Log**
      - Returns the logarithm of a specified number.
      - ``Log(1, 10)``
      - ``0d``
   *  - **Log10**
      - Returns the base 10 logarithm of a specified number.
      - ``Log10(1)``
      - ``0d``
   *  - **Max**
      - Returns the larger of two specified numbers.
      - ``Max(1, 2)``
      - ``2``
   *  - **Min**
      - Returns the smaller of two numbers.
      - ``Min(1, 2)``
      - ``1``
   *  - **Pow**
      - Returns a specified number raised to the specified power.
      - ``Pow(3, 2)``
      - ``9d``
   *  - **Round**
      - Rounds a value to the nearest integer or specified a number of decimal places. The mid number behavior can be changed by using EvaluateOption.RoundAwayFromZero during construction of the Expression object.
      - ``Round(3.222, 2)``
      - ``3.22d``
   *  - **Sign**
      - Returns a value indicating the sign of a number.
      - ``Sign(-10)``
      - ``-1``
   *  - **Sin**
      - Returns the sine of the specified angle.
      - ``Sin(0)``
      - ``0d``
   *  - **Sqrt**
      - Returns the square root of a specified number.
      - ``Sqrt(4)``
      - ``2d``
   *  - **Tan**
      - Returns the tangent of the specified angle.
      - ``Tan(0)``
      - ``0d``
   *  - **Truncate**
      - Calculates the integral part of a number.
      - ``Truncate(1.7)``
      - ``1``

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
      - Indicates whether the specified regular expression (second argument) finds a match in the specified input string (first argument).
      - ``match('1298-673-4192', '^[a-zA-Z0-9]\d{2}[a-zA-Z0-9](-\d{3}){2}[A-Za-z0-9]$')``
      - ``true``