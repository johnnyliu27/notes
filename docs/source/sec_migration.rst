
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

Neutron Transport in Pure Absorber with Fixed Point Source
----------------------------------------------------------

Exponential Decay Model
~~~~~~~~~~~~~~~~~~~~~~~

In pure absorber, the length each neutron traveled before absorption
will just be the same result as exponential decay model, in which

.. math:: 
   :label: eq::probability

   p(r) dr = e ^ {-\Sigma_a r} \Sigma_a dr

Then in this case the second moment of :math:`r` as

.. math::
   :label: eq::ExpoDecayModel

       \overline{r^2} = \int_{0}^{\infty} r^2 p(r) dr 
                      = \Sigma_a \int_{0}^{\infty} r^2 e ^ {-\Sigma_a r} dr
                      = \frac{2}{\Sigma_a^2}

Simple 1D Sphere
~~~~~~~~~~~~~~~~

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

Hollow 1D Sphere
~~~~~~~~~~~~~~~~

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

1D Sphere with 2 Regions
~~~~~~~~~~~~~~~~~~~~~~~~

Now if the sphere is solid but has two pure-absorber regions with
:math:`\Sigma_{ai}` for :math:`0 \leq r \leq R_0` and
:math:`\Sigma_{ao}` for :math:`r > R_0`. The scalar flux becomes

.. math::

   \label{eq::twoRegions}
       \phi(r) = 
        \begin{cases}
               \frac{S}{4 \pi r^2} e ^ {-\Sigma_{ai}}      & r \leq R_0    \\
               \frac{S}{4 \pi r^2} e ^ {-\Sigma_{ai} R_0 + \Sigma_{ao} (r-R_0)}  & r > R_0 \\
       \end{cases}

For :math:`r \leq R_0` the result is just the same as in the simple
solid sphere case in Equation :eq:`eq::probability`. For the case of
:math:`r > R_0`, the corresponding :math:`p(r)` and
:math:`\overline{r^2}` can be computed in the same vein and the results
are shown as

.. math::

   \begin{aligned}
       p(r)dr &=  \Sigma_{ao} e^{-\Sigma_{ai} R_0} e^{-\Sigma_a (r-R_0)} dr, \quad r > R_0
       \\
       \overline{r^2} &= \int_{0}^{R_0} r^2 p(r, r \leq R_0) dr + \int_{R_0}^{\infty} r^2 p(r, r > R_0) dr 
                       \\
                       &= \boxed{ \frac{2}{\Sigma_{ai}^2} +
                       e^{-\Sigma_{ai} R_0} \Bigg[  
                       \bigg( \frac{2}{\Sigma_{ao}^2} + \frac{2 R_0}{\Sigma_{ao}} + R_0^2 \bigg) -
                       \bigg( \frac{2}{\Sigma_{ai}^2} + \frac{2 R_0}{\Sigma_{ai}} + R_0^2 \bigg)
                       \Bigg] }
       \end{aligned}

Neutron Diffusion with 2 Regions
--------------------------------

Now let’s go back to NDE again for the two-region spherical geometry.
The sphere is solid but has two pure-absorber regions with
:math:`\Sigma_{ai}, D_{i}` for :math:`0 < r \leq R_0` and
:math:`\Sigma_{ao}, D_{o}` for :math:`r > R_0`. The 1D NDE in spherical
coordinates is

.. math:: \frac{d^2 \phi(r)}{dr^2} + \frac{2}{r} \frac{d \phi(r)}{dr} - \frac{\phi(r)}{M^2} = 0 \quad (r > 0)

To solve this equation, we can set :math:`u(r) = \phi(r) r`, then it
becomes

.. math:: \frac{d^2 u(r)}{dr^2} - \frac{u(r)}{M^2} = 0 \quad (r > 0)

The solution is

.. math:: u(r) = C_1 e^{-r/M} + C_2 e^{r/M}

For the inner and outer regions, we will have :math:`M_i^2` and
:math:`M_o^2` correspondingly. And the expression becomes

.. math::

   \label{}
       u(r) = 
        \begin{cases}
               C_1 e^{-r/M_i} + C_2 e^{r/M_i}      & r \leq R_0    \\
               C_3 e^{-r/M_o} + C_4 e^{r/M_o}      & r > R_0   \\
       \end{cases}

So according to :math:`u(r) = \phi(r) r`, the solution expression for
flux is

.. math::

   \label{}
       \phi(r) = 
        \begin{cases}
               C_1 \frac{e^{-r/M_i}}{r} + C_2 \frac{e^{r/M_i}}{r}  & r \leq R_0 \quad (\phi_i(r))  \\
               C_3 \frac{e^{-r/M_o}}{r}  + C_4 \frac{e^{r/M_o}}{r}     & r > R_0 \quad (\phi_o(r)) \\
       \end{cases}

There are 4 boundary conditions for solving for the 4 constants in the
expression. First, when :math:`r \rightarrow \infty`, :math:`\phi(r)`
must be finite value, thus we can get :math:`\boxed{C_4 = 0}`.

Secondly, since the source is located in the center of the sphere
(:math:`r=0`), there will be

.. math:: \lim_{r \to 0} 4 \pi r^2 J(r) = S

By using :math:`J(r) = -D \frac{d \phi(r)}{dr}`, we can get
:math:`\boxed{ C_1 + C_2 = \frac{S}{4 \pi D_i} }`.

The other two boundary conditions are the continuity of flux and current
at the interface of two regions (:math:`r = R_0`).

.. math::

   \begin{aligned}
           \phi_i(r) \rvert_{r = R_0} &= \phi_o\rvert_{r = R_0} \\
           - D_i \frac{d \phi_i(r)}{dr} \Bigg\rvert_{r = R_0} &= - D_o \frac{d \phi_o(r)}{dr} \Bigg\rvert_{r = R_0}
       \end{aligned}

Plugging in the expression of :math:`\phi_i(r)` and :math:`\phi_o(r)`,
they become

.. math::

   \begin{aligned}
           C_1 e^{-R_0/M_i} + C_2 e^{R_0/M_i}  &= C_3 e^{-R_0/M_o} \\
           D_i \Big[ \frac{R_0}{M_i} \big(C_1 e^{-R_0 / M_i} - C_2 e^{R_0/M_i} \big) + 
           \big(C_1 e^{-R_0 / M_i} + C_2 e^{R_0/M_i} \big) \Big] &=
           D_o \big( \frac{R_0}{M_o} + 1 \big) C_3 e^{-R_0 / M_o}
       \end{aligned}
