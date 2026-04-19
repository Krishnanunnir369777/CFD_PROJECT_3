Inverse PINN for Reynolds Number Recovery

Physics-Informed Neural Network project for recovering the Reynolds number from sparse flow observations around an ellipse.

Problem Statement

Using synthetic flow-field data generated from a forward PINN solution, estimate the unknown Reynolds number using an inverse PINN.

The network predicts:

u = streamwise velocity
v = cross-stream velocity
p = pressure

and simultaneously learns:

Reynolds number (Re)
Governing Equations

Steady incompressible 2D Navier–Stokes:

Continuity:

du/dx + dv/dy = 0

Momentum:

u du/dx + v du/dy + dp/dx − (1/Re)(d²u/dx² + d²u/dy²) = 0

u dv/dx + v dv/dy + dp/dy − (1/Re)(d²v/dx² + d²v/dy²) = 0

Domain

x ∈ [-6,15]
y ∈ [-6,6]

Ellipse:

Semi-major axis = 1
Semi-minor axis = 0.5
Boundary Conditions
Inlet: u = 1, v = 0
Outlet: p = 0
Top/Bottom walls: slip
Ellipse surface: no-slip
Features
Forward PINN for synthetic data generation
Inverse PINN for parameter recovery
Uniform sampling vs Wake-clustered sampling
Automatic plots and CSV tables
Run

pip install -r requirements.txt

python problem3_inverse_pinn.py

Example Results
True Re = 100
Uniform sampling converged at N = 70
Wake sampling converged at N = 30
Best recovered Re = 99.88
Output Folder

problem3_outputs/

Contains:

Flow contour plots
Streamlines
Training loss plots
Re vs N graphs
CSV tables
Author

Krishnanunni R
NIT Calicut
