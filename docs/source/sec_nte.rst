
Neutron Transport Equation
==========================

General form
------------

Based on neutrons' balance, the neutron transport equation (NTE) can
be summarized in a straight-forward relation as
:math:`R_{change} = R_{production} - R_{destruction}`, or equivalently
in the more common expression,

.. math:: 
   
  R_{change} + R_{destruction} = R_{production}

The general form of NTE is (referred to Equation (4-40) in Duderstadt &
Hamilton’s *Nuclear Reactor Analysis* in 1976)

.. math::

   \frac{\partial n(\vec{r}, E, \vec{\Omega}, t)}{\partial t} 
       + v \vec{\Omega} \cdot \nabla n(\vec{r}, E, \vec{\Omega}, t) 
       + v \Sigma_t(\vec{r}, E) n(\vec{r}, E, \vec{\Omega}, t) = 
       Q(\vec{r}, E, \vec{\Omega}, t)

Angular flux is defined as
:math:`\psi(\vec{r}, E, \vec{\Omega}, t) = n(\vec{r}, E, \vec{\Omega}, t) v`,
thus NTE can be re-written as

.. math::

  \boxed{
   \frac{1}{v} \frac{\partial \psi(\vec{r}, E, \vec{\Omega}, t)}{\partial t} + \vec{\Omega} \cdot \nabla \psi(\vec{r}, E, \vec{\Omega}, t) 
       + \Sigma_t(\vec{r}, E) \psi(\vec{r}, E, \vec{\Omega}, t) = 
       Q(\vec{r}, E, \vec{\Omega}, t)
  }

It should be mentioned here that across this document, the symbol
:math:`\psi` will be used for representing angular flux, and
:math:`\phi` for scalar flux, with
:math:`\phi(\vec{r}, E, t) = \int_{4\pi} \psi(\vec{r}, E, \vec{\Omega}, t) d\vec{\Omega}`.

The source term :math:`Q(\vec{r}, E, \vec{\Omega}, t)` is often composed
of three contributions: fission source :math:`Q_f`, scattering source
:math:`Q_s` and external source :math:`S(\vec{r}, E, \vec{\Omega}, t)`.
Thus

.. math:: Q(\vec{r}, E, \vec{\Omega}, t) = Q_f(\vec{r}, E, \vec{\Omega}, t) + Q_s(\vec{r}, E, \vec{\Omega}, t) + S(\vec{r}, E, \vec{\Omega}, t)

The external source is usually specified in advance, and less common in
general nuclear reactor physics simulations. For fission and scattering
source, they can be expressed as

.. math::

   \begin{aligned}
       & Q_f(\vec{r}, E, \vec{\Omega}, t) = \frac{\chi(E)}{4 \pi}  \int_{4\pi} \int_{0}^{\infty} \big[ \psi(\vec{r}, E', \vec{\Omega}, t) \nu(E') \Sigma_f(\vec{r}, E') \big] dE' d\vec{\Omega}
       \\
       & Q_s(\vec{r}, E, \vec{\Omega}, t) = \int_{4\pi} \int_{0}^{\infty} \big[ \psi(\vec{r}, E', \vec{\Omega}, t) \Sigma_s(\vec{r}, E' \rightarrow E, \vec{\Omega'} \rightarrow \vec{\Omega}) \big] dE' d\vec{\Omega}
       \end{aligned}

Steady State NTE
----------------

In steady state, the changing rate of neutron number density 
:math:`R_{change}` is equal to zero, thus
:math:`\frac{\partial \psi(\vec{r}, E, \vec{\Omega}, t)}{\partial t} = 0`.
So in steady state, NTE becomes

.. math::

  \boxed{
      \vec{\Omega} \cdot \nabla \psi(\vec{r}, E, \vec{\Omega}) 
       + \Sigma_t(\vec{r}, E) \psi(\vec{r}, E, \vec{\Omega}) = 
       Q(\vec{r}, E, \vec{\Omega})
  }

