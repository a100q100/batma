``batma.math`` --- Math Helpers
===============================

.. module:: batma.math
   :synopsis: Contains commonly used precalculated values and math functions.

:file: ``batma/maths/mathematic.py``

This module provides precalculated values, mathematical functions and an interface for the built-in math library.

Constants
---------

.. data:: e

   Represents the mathematical constant e.

.. data:: log10e

   Represents the log base ten of e.

.. data:: log2e

   Represents the log base two of e.

.. data:: pi

   Represents the value of pi.

.. data:: pi_over_2
   
   Represents the value of pi divided by two.

.. data:: pi_over_4

   Represents the value of pi divided by four.

.. data:: two_pi

   Represents the value of pi times two.


Functions
---------


.. function:: clamp(value, min_value, max_value)

   Restricts a value to be within a specified range. Returns ``min_value`` if 
   ``x < min_value``, ``max_value`` if ``x > max_value``, otherwise ``x``.


.. function:: distance(value1, value2)

   Calculates the absolute value of the difference of two values.


.. function:: inversesqrt(value)

   Returns ``1/sqrt(value)``.


.. function:: mod(a, b)
   
   Returns ``a%b``. This is just an equivalent for the %-operator.


.. function:: sign(value)

   Returns -1 with a negative argument, +1 with a positive argument, and 0 
   if its argument is zero.


.. function:: step(value, threshold)

   Returns 0 if ``value < threshold``, otherwise 1.


.. function:: wrap_angle(angle)

   Reduces a given angle to a value between π and -π.



Math Built-in Functions
-----------------------

Visit `python docs <http://docs.python.org/library/math.html>`_ for more 
informations.

=================== ================= =================== =====================
``abs(x)``          ``cosh(x)``       ``fsum(iterable)``  ``min(args)``        
``acos(x)``         ``degrees(x)``    ``gamma(x)``        ``modf(x)``          
``acosh(x)``        ``erf(x)``        ``hypot(x, y)``     ``pow(x, y[, z])``   
``asin(x)``         ``erfc(x)``       ``isinf(x)``        ``radians(x)``       
``asinh(x)``        ``exp(x)``        ``isnan(x)``        ``round(x[, n])``    
``atan(x)``         ``expm1(x)``      ``ldexp(x, i)``     ``sin(x)``           
``atan2(y, x)``     ``fabs(x)``       ``lgamma(x)``       ``sinh(x)``          
``atanh(x)``        ``factorial(x)``  ``log(x[, base])``  ``sqrt(x)``          
``ceil(x)``         ``floor(x)``      ``log10(x)``        ``tan(x)``           
``copysign(x, y)``  ``fmod(x, y)``    ``log1p(x)``        ``tanh(x)``          
``cos(x)``          ``frexp(x)``      ``max(args)``       ``trunc(x)``         
=================== ================= =================== =====================