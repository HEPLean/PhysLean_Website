---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
# To see the site locally:
# Run
# To view changes run: bundle exec jekyll serve
#layout: home
---

# Project ideas 

Below are a list of project ideas, no matter who you are, you may attempt any of these.
You should assume that this list is up-to date. They are roughly ordered in complexity 
from easiest to hardest. If you would like to 'claim' one of these projects or 
add projects let Joseph Tooby-Smith know, 
or make a pull-request to the PhysLean [website repo](https://github.com/HEPLean/PhysLean_Website).

### Planck’s theory of blackbody radiation
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Formalize Planck's law (see [here](https://en.wikipedia.org/wiki/Planck%27s_law#The_law)) for 
blackbody radiation, and derive Wien's displacement law (see [here](https://en.wikipedia.org/wiki/Wien%27s_displacement_law#Derivation_from_Planck's_law)).

### Hydrodynamic drag 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Write down Newton's second law for a particle with a hydrodynamic drag trapped in a harmonic spring, 
and derive from that a differential equation for the mean-squared displacement. 
See [here](https://mmathphys.physics.ox.ac.uk/sites/default/files/mmathphys/documents/media/nonequilibrium_statistical_physics_2018.pdf).

### The reflectionless potential in quantum mechanics 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Formalize the properties of the [reflectionless potential](https://arxiv.org/pdf/2411.14941) in 
quantum mechanics, following the formalization of the quantum harmonic oscillator. 

### Tight-binding model for graphene 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

PhysLean already contains the tight-binding model for a chain. This project would 
aim to generalize that to do the tight-binding model for graphene. A reference 
can be found [here](https://cpb-us-w2.wpmucdn.com/u.osu.edu/dist/3/67057/files/2018/09/graphene_tight-binding_model-1ny95f1.pdf). 

### Definition of the bosonic and fermionic Hilbert spaces 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Define the Hilbert space of a single bosonic and a single fermionic particle. These 
can be found in these [note](https://souravchatterjee.su.domains/qft-lectures-combined.pdf#page23). 
Part of this will involve defining the Lorentz-invariant measure and the mass-shell manifold. 

### Basic properties of cosmology 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Within PhysLean there are currently some informal results related to the FLRW metric,
these appear in [this](https://github.com/HEPLean/PhysLean/blob/master/PhysLean/Cosmology/FLRW/Basic.lean) file. 
The aim of this project would be to formalize into Lean those results, and expand upon them. 
See a related discussion [here](https://leanprover.zulipchat.com/#narrow/channel/479953-PhysLean/topic/Cosmology.20Project.20and.20dependencies/with/512468525).

### Boltzmann equation 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Write down the Boltzmann equation with the BGK collision operator and prove basic properties 
about solutions thereof. See, amongst other places, [this](https://mmathphys.physics.ox.ac.uk/sites/default/files/mmathphys/documents/media/kt_2019.pdf).

### Larmor formula (Power radiated by a non-relativistic particle)
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

The [Larmor formula](https://en.wikipedia.org/wiki/Larmor_formula) gives the power 
radiated by a non-relativistic point particle as it accelerates. The idea of this project 
would be to derive this formula using the foundations of electromagnetism. 

### Quantum particle on a ring 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Formalize the quantum mechanics of a particle on a ring, see 
e.g. the [wikipedia page](https://en.wikipedia.org/wiki/Particle_in_a_ring). 
See also, [this](https://leanprover.zulipchat.com/#narrow/channel/479953-PhysLean/topic/QM.20particle.20on.20a.20ring/with/523260615)
Zulip discussion. 

### The two Higgs doublet model potential 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

The aim of this project would be to prove Theorem 1, 2 & 4 of this
[arXiv(hep-ph):0605184](https://arxiv.org/pdf/hep-ph/0605184). This is related to the 
two Higgs doublet model, which corresponds to a model of the universe with a proposed 
extra Higgs doublet. 

### Properties of grand unified theory groups 
<p class="badge badge-primary" style="background-color: rgba(129, 22, 67, 0.1);color: #690080;">Available</p> 

Prove the group theoretic properties of the grand-unified theories: SU(5), Spin(10) and Pati-Salam, 
as they appear in [this note](https://math.ucr.edu/home/baez/guts.pdf).
Some of these results appear on the [todo list](/TODOList).

