Youngs and Cramer Recursive Formula: Extension to Covariance Matrix
###################################################################

:date: 2017-03-09 12:59
:tags: calculus
:category: maths
:slug: Youngs and Cramer's covariance matrix formula.
:summary: Calculus details of Youngs And Cramer's recursive covariance matrix formula.


Previously we showed that the sum of square differences
:math:`S_{1,n} = \sum_{i=1}^n (x_i - \frac{1}{n} T_{1,n})^2`, where
:math:`T_{1,n} = \sum_{i=1}^n x_i` satisfies the following
recursive equality

.. math::

   S_{1,m+n} = S_{1,m} + S_{m+1,m+n} + \frac{m}{(m+n)n} \left(
      \frac{n}{m} T_{1,m} - T_{m+1,m+n}
   \right)^2


Denoting by :math:`X_{1,n} = \sum_{i=1}^n x_i` and :math:`Y_{1,n} = \sum_{i=1}^n y_i`,
Let us show that the sum of products

.. math::

   C_{1,n} = \sum_{i=1}^n (x_i - \frac{1}{n} X_{1,n})
                          (y_i - \frac{1}{n} Y_{1,n})


satisfies the following recursive equality

.. math::

   C_{1,m+n} = C_{1,m} + C_{m+1,m+n} + \frac{m}{(m+n)n}
      \left( \frac{n}{m} X_{1,m} - X_{m+1,m+n} \right)
      \left( \frac{n}{m} Y_{1,m} - Y_{m+1,m+n} \right)


Notice the similarity between the two recursive formula between :math:`S_{1,n}`
and :math:`C_{1,n}`.

We use exactly the same technique as in the recursive formula of
:math:`S_{1,n}`.

.. math::

   C_{1,m+n} = \sum_{i=1}^{m+n} (x_i - \frac{1}{m+n} X_{1,m+n})(y_i -
   \frac{1}{m+n} Y_{1_,m+n})

We break down :math:`C_{1,m+n}` into two terms

.. math::

   A_{m,n} = \sum_{i=1}^{m} (x_i - \frac{1}{m+n} X_{1,m+n})(y_i -
   \frac{1}{m+n} Y_{1_,m+n})

   B_{m,n} = \sum_{i=m+1}^{m+n} (x_i - \frac{1}{m+n} X_{1,m+n})(y_i -
   \frac{1}{m+n} Y_{1_,m+n})


Expanding the two terms

.. math::

   A_{m,n} = C_{1,m} + m(\frac{1}{m} X_{1,m} - \frac{1}{m+n} X_{m+1,m+n})
                        (\frac{1}{m} Y_{1,m} - \frac{1}{m+n} Y_{m+1,m+n})

   B_{m,n} = C_{m+1,m+n} + n(\frac{1}{n} X_{m+1,m+n} - \frac{1}{m+n} X_{1,m})
                            (\frac{1}{n} Y_{m+1,m+n} - \frac{1}{m+n} Y_{1,m})


Expanding again:

.. math::

   A_{m,n} = C_{1,m} + \frac{m}{(m+n)^2}
    (  \frac{n^2}{m^2} X_{1,m} Y_{1,m} + X_{m+1,m+n} Y_{m+1,m+n}
     - \frac{n}{m} X_{m+1,m+n} Y_{1,m} - \frac{n}{m} X_{m+1,m+n} Y_{m+1,m+n})

   B_{m,n} = C_{m+1,m+n} + \frac{n}{(m+n)^2}
    (  \frac{m^2}{n^2} X_{m+1,m+n} Y_{m+1,m+n} + X_{1,m} Y_{1,m}
     - \frac{m}{n} X_{m+1,m+n} Y_{1,m} - \frac{m}{n} X_{m+1,m+n} Y_{m+1,m+n})


Summing the two terms:

.. math::

   C_{1,m+n} = C_{1,m} + C_{m+1,m+n} +
    \frac{1}{(m+n)^2} (   (\frac{n^2}{m} + n) X_{1,m} Y_{1,m}
                        + (\frac{m^2}{n} + m) X_{m+1,m+n} Y_{m+1,m+n}
                        - (m+n) X_{1,m} Y_{1,m}
                        - (m+n) X_{m+1,m+n} Y_{m+1,m+n} )

   C_{1,m+n} = C_{1,m} + C_{m+1,m+n} +
    \frac{1}{(m+n)} (   \frac{n}{m} X_{1,m} Y_{1,m}
                        + \frac{m}{n} X_{m+1,m+n} Y_{m+1,m+n}
                        - X_{1,m} Y_{1,m}
                        - X_{m+1,m+n} Y_{m+1,m+n} )

   C_{1,m+n} = C_{1,m} + C_{m+1,m+n} +
    \frac{1}{(m+n)}
    (\sqrt(\frac{n}{m}) X_{1,m} - sqrt{\frac{m}{n}} X_{m+1,m+n})
    (\sqrt(\frac{n}{m}) Y_{1,m} - sqrt{\frac{m}{n}} Y_{m+1,m+n})

   C_{1,m+n} = C_{1,m} + C_{m+1,m+n} +
    \frac{m}{n(m+n)}
    (\frac{n}{m} X_{1,m} - X_{m+1,m+n}) (\frac{n}{m} Y_{1,m} - Y_{m+1,m+n})
