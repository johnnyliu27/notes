
Neutron Diffusion Equation
==========================

General form
------------

Based on neutrons’ balance, in non-multiplying and multiplying systems,
the general steady-state diffusion equation can be written as

.. math::
  :label: eq1

   \begin{gathered}
    \label{eq1}
       - \nabla J (\vec{r},E) + \Sigma_t (\vec{r},E) \phi (\vec{r},E) = 
       \int_0^\infty \Sigma_s (\vec{r},E' \rightarrow E) \phi (\vec{r},E') dE'  \\
       + \begin{cases}
               S (\vec{r},E),  & \text{non-multiplying} \\
               \frac{\chi(E)}{k} \int_0^\infty \nu \Sigma_f (\vec{r},E') \phi (\vec{r},E') dE', & \text{multiplying}    \\
       \end{cases}\end{gathered}
       

Using Fick’s law, the neutron current :math:`J (\vec{r},E)` can be
expressed by flux :math:`\phi(\vec{r},E)` in the following relationship,

.. math:: J (\vec{r},E) = - D(\vec{r},E) \nabla \phi (\vec{r},E)
  :label: eq2

then Equation :eq:`eq1` can be rewritten as

.. math::
  :label: eq3

   \begin{gathered}
    \label{eq3}
       - { \nabla D(\vec{r},E) \nabla \phi (\vec{r},E)} + \Sigma_t (\vec{r},E) \phi (\vec{r},E) = 
       \int_0^\infty \Sigma_s (\vec{r},E' \rightarrow E) \phi (\vec{r},E') dE' \\
       + \begin{cases}
                   S (\vec{r},E),  & \text{non-multiplying} \\
                   \frac{\chi(E)}{k} \int_0^\infty \nu \Sigma_f (\vec{r},E') \phi (\vec{r},E') dE', & \text{multiplying}  \\
           \end{cases}\end{gathered}

Multi-group form
----------------

In practice, neutron diffusion equations (NDE) and neutron transport
equations (NTE) often show up in multi-group form. Rewriting Equation
:eq:`eq3`, the multi-group form of NDE is

.. math::
  :label: eq4

   \begin{gathered}
       -{\nabla D_g(\vec{r}) \nabla \phi_g (\vec{r})} + \Sigma_{t,g} (\vec{r}) \phi_g (\vec{r}) = 
       \sum_{g'=1}^G \Sigma_{s,g' \rightarrow g} (\vec{r}) \phi_{g'} (\vec{r}) \\
       +   \begin{cases}
               S_g (\vec{r}) , & \text{non-multiplying} \\
               \frac{\chi_g}{k} \sum_{g'=1}^G \nu \Sigma_{f,g'} (\vec{r}) \phi_{g'} (\vec{r}), & \text{multiplying} \\
           \end{cases}\end{gathered}

One-group form
--------------

To further simplify NDE, we can treat the whole energy range of neutron
as one broad group, which will result in the one-group or one-speed
diffusion theory. The one-group NDE is

.. math::
  :label: eq5

   \label{eq5}
       - \nabla D(\vec{r}) \nabla \phi(\vec{r}) + \Sigma_a(\vec{r}) \phi(\vec{r}) = 
       \begin{cases}
           S(\vec{r}) , & \text{non-multiplying} \\
           \frac{1}{k} \nu \Sigma_f(\vec{r}) \phi(\vec{r}) , & \text{multiplying} \\
       \end{cases}

If the material is homogeneous, then the cross sections and diffusion
coefficients will be independent of spatial variable, which will give
:math:`- \nabla D(\vec{r}) \nabla \phi(\vec{r}) = - D(\vec{r}) \nabla^2 \phi(\vec{r})`.
In addition, if we neglect the spatial variable :math:`\vec{r}` in Equation
:eq:`eq5` for simplicity, it can be rewritten in a clearer format
as

.. math::
  :label: eq6

   \label{eq6}
       \begin{cases}
           - D \nabla^2 \phi + \Sigma_a \phi = S , & \text{non-multiplying} \\
           - D \nabla^2 \phi + \Sigma_a \phi = \frac{1}{k} \nu \Sigma_f \phi , & \text{multiplying} \\
       \end{cases}

To make the equation into the general format of ordinary differential
equations (ODE), for non-multiplying system, by re-arranging the first
equation in Equation :eq:`eq6`, we can get

.. math::
  :label: eq7

   \label{eq7}
       \nabla^2 \phi - \frac{\Sigma_a}{D} \phi = -\frac{S}{D} \qquad \Rightarrow \qquad \nabla^2 \phi - \frac{1}{L^2} \phi = -\frac{S}{D}

in which :math:`L^2 = \frac{D}{\Sigma_a}`. Then we can get the
homogeneous version of Equation :eq:`eq7` by setting the constant
term on RHS as 0, shown as

.. math::
  :label: eq8

   \label{eq8}
       \boxed{ \nabla^2 \phi - \frac{1}{L^2} \phi = 0 }

For multiplying system, by re-arranging the second equation in Equation
:eq:`eq6`, we can get

.. math::
  :label: eq9

   \label{eq9}
        \nabla^2 \phi + \frac{ \frac{\nu \Sigma_f}{k} - \Sigma_a }{D} \phi = 0

Let :math:`B^2 = \frac{ \frac{\nu \Sigma_f}{k} - \Sigma_a }{D}`, we can
get the general form for multiplying system as

.. math::
  :label: eq10

   \label{eq10}
       \boxed{ \nabla^2 \phi + B^2 \phi = 0 }

At the end, the equations we will often see and need to solve in
non-multiplying and multiplying systems can be summarized as

.. math::
  :label: eq11

   \label{eq11}
       \begin{cases}
           \nabla^2 \phi - \frac{1}{L^2} \phi = 0  , & \text{non-multiplying} \\
           \nabla^2 \phi + B^2 \phi = 0 , & \text{multiplying} \\
       \end{cases}

To solve them, first we need to write out the explicit expression of the
Laplace operator :math:`\nabla^2` in different coordinate systems, which
can be found in Appendix A of the textbook used for course 22.05.
