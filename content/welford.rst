Welford's Recursive Variance Formula
####################################

:date: 2017-03-07 16:45
:tags: calculus
:category: maths
:slug: Welford
:summary: Calculus details of Welford's recursive variance formula


We detail the calculation of the recursive formula:

.. math::

   S_n = \sum_{i=1}^n (x_i - \bar{x}_n)^2

We introduce :math:`\bar{x}_{n-1}` to relate :math:`S_n` with :math:`S_{n-1}`:

.. math::
   S_n = \sum_{i=1}^n ((x_i - \bar{x}_{n-1}) + (\bar{x}_{n-1} - \bar{x}_n))^2

We expand the expression:

.. math::
   S_n = \sum_{i=1}^n (x_i - \bar{x}_{n-1})^2 + n(\bar{x}_{n-1} - \bar{x}_n)^2
         - 2 (\bar{x}_{n-1} - \bar{x}_n) \sum_{i=1}^n (x_i - \bar{x}_{n-1})

   S_n = \sum_{i=1}^n (x_i - \bar{x}_{n-1})^2 + n(\bar{x}_{n-1} - \bar{x}_n)^2
         - 2 n (\bar{x}_{n-1} - \bar{x}_n) (\bar{x}_n - \bar{x}_{n-1})

   S_n = \sum_{i=1}^n (x_i - \bar{x}_{n-1})^2 - n(\bar{x}_{n-1} - \bar{x}_n)^2

   S_n = S_{n-1} + (x_n - \bar{x}_{n-1})^2 - n (\bar{x}_{n-1} - \bar{x}_n)^2


Using the relation between the mean :math:`\bar{x}_n` and :math:`\bar{x}_{n-1}`

.. math::

   n \bar{x}_n = (n-1) \bar{x}_{n-1} + x_n


Then observing the following equality:

.. math::

   x_n - \bar{x}_{n-1} = n (\bar{x}_n - \bar{x}_{n-1})


Using the first equality, we can reduce the last two terms in :math:`S_n`

.. math::

   S_n = S_{n-1} + n(n-1) (\bar{x}_n - \bar{x}_{n-1})^2

Then by reordering a bit:

.. math::

   S_n = S_{n-1} + n (\bar{x}_n - \bar{x}_{n-1}) \times (n-1) (\bar{x}_n - \bar{x}_{n-1})


We recognize:

.. math::

   S_n = S_{n-1} + (x_n - \bar{x}_{n-1}) \times (n-1) (\bar{x}_n - \bar{x}_{n-1})

   S_n = S_{n-1} + (x_n - \bar{x}_{n-1}) \times \frac{n-1}{n} (x_n - \bar{x}_{n-1})


But we know

.. math::

   \bar{x}_{n-1} = \frac{n \bar{x}_n - x_n}{n-1}

   x_n - \bar{x}_{n-1} = \frac{n}{n-1} (x_n - \bar{x}_n)


We replace the rightmost term in :math:`S_n` and we finally get

.. math::

   S_n = S_{n-1} + (x_n - \bar{x}_{n-1}) (x_n - \bar{x}_n)

This is the expected formula as displayed in wikipedia.
