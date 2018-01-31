
Migration Area
==============

Classical Definition in One-group Diffusion
-------------------------------------------

In one-group diffusion theory, migration area can be proven to be equal
to one-sixth of the average square of the flight distance from the
position where a neutron is born to the position where it is absorbed,
as shown in Equation :eq:`eq::ma_defination`.

.. math::
   :label: eq::ma_defination

       M^2 =\frac{D}{\Sigma_{a}} = \frac{1}{6} \overline{r^2}

In Equation :eq:`eq::ma_defination`, :math:`M^2`
is migration area, :math:`D` is diffusion coefficient,
:math:`\Sigma_{a}` is absorption cross section and
:math:`\overline{r^2}` is the average square of crow flight length of
the neutron from the position where it is born to the position absorbed.

The derivation of this one-sixth relationship is under the assumption of
a point neutron source emitting neutrons (with the intensity of
:math:`S`) in an infinite homogeneous material. Through one-group
diffusion theory, the spatial scalar flux expression in polar
coordinates can be derived as

.. math::

   \label{eq::flux_diffusion}
       \phi(r) = \frac{S e^{-r/M}}{4 \pi r D}

With this, the probability of any neutron absorbed within a thin
spherical shell from :math:`r` to :math:`r+dr` is

.. math::
   :label: eq::probability_abs
   
       p(r)dr = \frac{\Sigma_a \phi(r) dV}{S}
               = \frac{\Sigma_a \frac{S e^{-r/M}}{4 \pi r D} 4 \pi r^2 dr}{S}
               = \frac{1}{M^2} e^{-r/M} r dr

Using the probability density function for :math:`r` with the
integration formula of
:math:`\int_{0}^{\infty} r^n e^{-ar} dr = \frac{n!}{a^{n+1}}`, we can
compute the second moment of :math:`r` as

.. math::
   :label: eq::second_moment

       \overline{r^2} = \int_{0}^{\infty} r^2 p(r) dr 
                      = \frac{1}{M^2} \int_{0}^{\infty} r^3 e^{-r/M} dr
                      = \frac{1}{M^2} \frac{3!}{(1/M)^4} = 6 M^2

So we can get the relationship of
:math:`M^2 = \frac{1}{6} \overline{r^2}`.

Pure Absorber with Fixed Point Source
-------------------------------------

Exponential Decay Model
~~~~~~~~~~~~~~~~~~~~~~~

In pure absorber, the length each neutron traveled before absorption
will just be the same result as exponential decay model, in which

.. math:: p(r) dr = e ^ {-\Sigma_a r} \Sigma_a dr

Then in this case the second moment of :math:`r` as

.. math::
   :label: eq::ExpoDecayModel
   
       \overline{r^2} = \int_{0}^{\infty} r^2 p(r) dr 
                      = \Sigma_a \int_{0}^{\infty} r^2 e ^ {-\Sigma_a r} dr
                      = \frac{2}{\Sigma_a^2}

Neutron Transport in Simple 1D Sphere
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Without solving the NTE, based on the geometrical and exponential decay
of the scalar neutron flux in simple 1D homogeneous sphere filled with
pure absorber, we can get

.. math:: \phi(r) = \frac{S}{4 \pi r^2} e ^ {-\Sigma_a r}

Then repeating the same process of computing :math:`p(r)` and
:math:`\overline{r^2}` as shown in Equation
:eq:`eq::probability_abs` and Equation
:eq:`eq::second_moment`, we can get

.. math::

   \begin{aligned}
       & p(r)dr = \frac{\Sigma_a \phi(r) dV}{S}
                   = \frac{\Sigma_a \frac{S}{4 \pi r^2} e ^ {-\Sigma_a r}  4 \pi r^2 dr}{S}
                   = \Sigma_a e^{-\Sigma_a r} dr
       \\
       & \overline{r^2} = \int_{0}^{\infty} r^2 p(r) dr 
                          = \Sigma_a \int_{0}^{\infty} r^2 e ^ {-\Sigma_a r} dr
                          = \boxed{\frac{2}{\Sigma_a^2}}
       \end{aligned}

This just shows the same result as the exponential decay model in
Equation :eq:`eq::ExpoDecayModel`.

Neutron Transport in Hollow 1D Sphere
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now if we consider a sphere with a hollow inner part whose radius is
:math:`R_0`, the geometrical decay remains unaffected, but the
exponential decay will only affect when :math:`r>R_0`. As a result, the
scalar flux becomes

.. math::

   \label{eq::hollowSphere}
       \phi(r) = 
        \begin{cases}
               \frac{S}{4 \pi r^2}     & r \leq R_0    \\
               \frac{S}{4 \pi r^2} e ^ {-\Sigma_a (r-R_0)}  & r > R_0  \\
       \end{cases}

Then repeating the same process again of computing :math:`p(r)` and
:math:`\overline{r^2}` as Equation
:eq:`eq::probability_abs` and Equation
:eq:`eq::second_moment`, when :math:`r > R_0`, we
can get

.. math::

   \begin{aligned}
       & p(r)dr = \frac{\Sigma_a \phi(r) dV}{S}
                   = \frac{\Sigma_a \frac{S}{4 \pi r^2} e ^ {-\Sigma_a (r-R_0)}  4 \pi r^2 dr}{S}
                   = \Sigma_a e^{-\Sigma_a (r-R_0)} dr, \quad r > R_0
       \\
       & \overline{r^2} = \int_{R_0}^{\infty} r^2 p(r) dr 
                          = \Sigma_a \int_{R_0}^{\infty} r^2 e ^ {-\Sigma_a (r-R_0)} dr
                          = \Sigma_a \int_{0}^{\infty} (t+R_0)^2 e ^ {-\Sigma_a t} dt
                          = \boxed{ \frac{2}{\Sigma_a^2} + \frac{2 R_0}{\Sigma_a} + R_0^2 }
       \end{aligned}

It’s easy to find out that in the simple solid 1D sphere geometry,
:math:`\overline{r^2} = \frac{2}{\Sigma_a^2}`, while in the hollow case
it’s
:math:`\overline{r^2} = \frac{2}{\Sigma_a^2} + \frac{2 R_0}{\Sigma_a} + R_0^2`.
The extra two terms :math:`(\frac{2 R_0}{\Sigma_a} + R_0^2)` in the
hollow case proposes the difficulty for treating the vacuum-crossing
flights of neutrons in the tallies of incremental migration area.
