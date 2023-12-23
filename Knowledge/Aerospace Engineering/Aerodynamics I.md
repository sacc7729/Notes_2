# Prequisites
[[Aircraft I]]
# References
Fundamental of Aerodynamics

# Assumptions
We assume the mean free path is large (e.g. molecules can go relatively far without bumping into each other), this is called continuum mechanics (e.g. we treat the body of fluid as a continuum instead of individual molecules).

# Basic Terms
density: $\rho$
velocity: $\vec{v}$ 
$\vec{i}$ component of $\vec{v}$: $v_i$
volume: V
surface: s
distance: s (oops)
heat exchanged: q
vorticity is the curl of the velocity: $\nabla \times \vec{v}$

A pathline is the path a fluid will take.  A streamline is the velocity at each point in fluid.  If the flow is steady (e.g. not changing with time) then these values are the same.


# Conservation Equations

## Continuity Equation

The continuity equation states that any fluid going through an area is equal to the change in the fluid surrounded by the area:
$$
\iint_{closed} \rho \vec{v} \circ d\vec{s} = 
- \frac{\partial}{\partial t} \iiint_{closed} \rho dV 
$$

For any one point:
$$
\frac{\partial \rho}{\partial t} = - \nabla \cdot \rho \vec{v}  
$$

In some cases we can make the assumption that $\frac{\partial}{\partial t} = 0$ (i.e. the fluid is steady).

## Momentum Equation

We want to show $\vec{F}=\dot{\vec{p}}$ in a different form.

For $\vec{F}$ we have:
$$
\vec{F}_{total} = \vec{F}_{body} + \vec{F}_{surface} + \vec{F}_{viscuous}
$$
where $F_{body}$ are the forces felt body by the parcel body (e.g. magnetism and gravity) and $F_{surface}$ are the forces on the surface (e.g. pressure).

More verbosely this becomes

$$
\vec{F}_{total} = \iiint_{closed} \rho \vec{f} dV  - \iint_{closed} \rho ds + \vec{F}_{viscuous}
$$

For $\dot{\vec{p}}$ we have the net flow of volume out of the parcel and the change of momentum inside the volume:
$$
\dot{\vec{p}} = \iint_{closed} \rho \vec{v} \circ d\vec{s} \vec{v} +
\frac{\partial}{\partial t} \iiint_{closed} \rho \vec{v} dV
$$

which gives us

$$
\iiint_{closed} \rho \vec{f} dV  - \iint_{closed} \rho d\vec{s} + \vec{F}_{viscuous}
= \iint_{closed} \rho \vec{v} \circ d\vec{s} \vec{v} +
\frac{\partial}{\partial t} \iiint_{closed} \rho \vec{v} dV
$$

For fluids that are steady, inviscid, and have no body forces we have:

$$
\iint_{closed}\rho \vec{v} \circ ds \vec{v} = - \iint_{closed}\rho d\vec{s}
$$
which can give us the Euler momentum equation:
$$
\nabla \circ \rho v_i \vec{v} = - \frac{\partial p}{\partial v_i}
$$

If we factor in viscous flow we get the Navier Stokes momentum equation.

## Energy equation

We only consider energy transfer in the form of heat or work.

The change of energy due to heat is given as

$$
\dot{Q} = \iiint_{closed}\dot{q} \rho dV + \dot{Q}_{viscous}
$$

Rate of work done due to pressure and body forces is

$$
-\iint_{closed}\rho d\vec{s} \circ \vec{v} + \iiint_{closed} \rho \vec{f} dV \circ \vec{v} + \dot{W}_{viscous} 
$$

We can think of the energy inside some volume in terms of internal energy $e = c_v T$ and kinetic energy $\frac{\vec{v}^2}{2}$.

The change in energy across the surface and within the volume is:

$$
\iint_{closed} \rho \vec{v} \circ d\vec{s} (e + \frac{\vec{v}^2}{2})
+ \frac{\partial}{\partial t} \iiint_{closed} \rho (e + \frac{\vec{v}^2}{2}) dV
$$

Combining we get:
$$
\iiint_{closed}\dot{q} \rho dV + \dot{Q}_{viscous} - 
\iint_{closed}\rho d\vec{s} \circ \vec{v} + \iiint_{closed} \rho \vec{f} dV \circ \vec{v} + \dot{W}_{viscous} =
\iint_{closed} \rho \vec{v} \circ d\vec{s} (e + \frac{\vec{v}^2}{2})
+ \frac{\partial}{\partial t} \iiint_{closed} \rho (e + \frac{\vec{v}^2}{2}) dV
$$

If the flow is steady, inviscid, and adiabatic we have

$$
\iint_{closed} \rho (e + \frac{\vec{v}^2}{2}) \vec{v} \circ d\vec{s} =
- \iint_{closed} \rho \vec{v} \circ d \vec{s}
$$


# Solving in the Real World

If $\rho$ is constant then we can use the continuity equation and the momentum equation to solve for $\vec{v}$ and $\vec{p}$.  Where $\rho$ is variable, we need to also use the energy equation.

Combining the continuity, momentum, and energy equation gives us a set of differential equations known as the Navier Stokes equations.

Typically if we want to solve these equations we have to use computational fluid dynamics (e.g. numerical methods from a computer to solve).  Sometimes it's also easier to get the results experimentally (e.g. put the body into a wind tunnel).  NACA has a bunch of useful approximations for different bodies in different aeronautical conditions.

# Useful Approximations

## Inviscid, Incompressible

### Bournoulli

Bournoulli's equation can be derived from momentum equation in one dimention:

$$
dp = - \rho \vec{v} d\vec{v}
$$

### Elementary Fluid Movements
* Uniform
* Source
* Doublet
* Vortex

###  Kutta - Joukowski

If we sum up all the pressures around a path we get lift.  It can conveniently be written as:

$$
L = \rho v_{net} \Gamma
$$

where $\Gamma$ is circulation
$$
\Gamma = - \int_{closed} \vec{v} \circ d\vec{s}
$$

Technically we can only ever have lift with friction but we can describe lift using inviscid theories.  

## Inviscid, Compressible
This is the regime of shock waves and hypersonics.

## Viscid, Compressible

This gives rise to boundary layers and turbulence.  Technically friction is required for lift even though it can be described using inviscid theories.