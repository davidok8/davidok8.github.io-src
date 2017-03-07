Youngs and Cramer Recursive Formula
###################################

:date: 2017-03-07 17:39
:tags: calculus
:category: maths
:slug: Youngs and Cramer
:summary: Calculus details of Youngs And Cramer's recursive variance formula



.. math::

   S_{1, m+n} = \sum_{i=1}^{m+n} (x_i - \frac{1}{m+n} T_{1, m+n})^2

   S_{1, m+n} =
    \underbrace{\sum_{i=1}^{m} (x_i - \frac{1}{m+n} T_{1,m+n})^2}_{A_{m,n}} +
    \underbrace{\sum_{i=m+1}^{m+n} (x_i - \frac{1}{m+n} T_{1, m+n})^2}_{B_{m,n}}


Denote by

.. math::
   A_{m,n} = \sum_{i=1}^{m} (x_i - \frac{1}{m} T_{1, m+n})^2

   B_{m,n} = \sum_{i=m+1}^{m+n} (x_i - \frac{1}{m} T_{1, m+n})^2


Then we expand :math:`A_{m,n}` by introducing :math:`\frac{1}{m} T_{1,m}`

.. math::

   A_{m,n} = \sum_{i=1}^{m} (x_i - \frac{1}{m} T_{1,m} +
   \frac{1}{m} T_{1,m} - \frac{1}{m+n} T_{1, m+n})^2

We end up with

.. math::

   A_{m,n} = S_{1,m} + m (\frac{1}{m} T_{1,m} - \frac{1}{m+n} T_{1,m+n})^2


Then using :math:`T_{1,m+n} = T_{1,m} + T_{m+1,n+1}`

.. math::

   A_{m,n} = S_{1,m} + \frac{m}{(m+n)^2} (\frac{n}{m} T_{1,m} - T_{m+1,m+n})^2


Likewise we expand :math:`B_{m,n}` by introducing :math:`\frac{1}{n} T_{m+1,m+n}`

.. math::
   B_{m,n} = S_{m+1,m+n} + n (\frac{1}{n} T_{m+1,m+n} - \frac{1}{m+n} T_{1,m+n})^2

   B_{m,n} = S_{m+1,m+n} + \frac{n}{(m+n)^2} (\frac{m}{n} T_{m+1,m+n} - T_{1,m})^2


Substituting back :math:`A_{m,n}` and :math:`B_{m,n}` in :math:`S_{m,n}`

.. math::

   S_{1,m+n} = S_{1,m} + S_{m+1,m+n} + \frac{1}{(m+n)^2} \left( 
      \frac{(m+n)n}{m} T_{1,m}^2
    + \frac{(m+n)n}{m} T_{m+1,m+n}^2
    - 2(m+n) T_{1,m} T_{m+1,m+n}
   \right)

   S_{1,m+n} = S_{1,m} + S_{m+1,m+n} + \frac{1}{m+n} \left( 
      \frac{n}{m} T_{1,m}^2
    + \frac{m}{n} T_{m+1,m+n}^2
    - 2 T_{1,m} T_{m+1,m+n}
   \right)

   S_{1,m+n} = S_{1,m} + S_{m+1,m+n} + \frac{1}{m+n} \left( 
      \sqrt{\frac{n}{m}} T_{1,m} - \sqrt{\frac{m}{n}} T_{m+1,m+n}
   \right)^2

   S_{1,m+n} = S_{1,m} + S_{m+1,m+n} + \frac{m}{(m+n)n} \left( 
      \frac{n}{m} T_{1,m} - T_{m+1,m+n}
   \right)^2
