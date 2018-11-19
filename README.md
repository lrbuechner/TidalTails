# Tidal Tails
Soon to be complete algorithm to detect the presence of open cluster tidal tails in the Milky Way

The main project is the "Hyatails" notebook


# To outline what I’ve done so far
1.  ADQL search parameters informed by literature: (parallax > 5 and pmra_error < .1 and pmdec_error < .1 and parallax_error < .1 and radial_velocity_error < 1)

2. With my initial data I filtered out the stars with tangential velocities outside a generous interval based off the distribution of the core members in EQ-coordinates then converted those stars to 6-D space (galactic coordinates) using the astropy package.
 
3.  Filtered out stars with velocities outside a 2.5 km/s interval around the average space velocity of the core. (2.5km/s comes from one of the papers, pretty sure that figure comes from theoretical models of predicted dispersion after cluster genesis up to now). Leaving me with around 5 stars. 

4. Set the Hyades as the origin of a sphere using the center estimated from my previous analysis of it's core and created a function that iterates over theta and phi at different values of rho. For each of these partitions I then use a function that determines the point of convergence on all of the stars laying within that region. 

5. Calculate the proportion of the stars within that region that pass through the point of convergence and if the estimated point of convergence lies within a pre-defined, looser definition of the point of convergence estimated from the core members. I haven’t decided how I want to visualize the percentages. If the estimated POC is within that box, I add to a bucket in a 3d histogram whose base axes are D = [0,2pi] x [0,pi]. Hopefully there are two peaks signifying the position of the tidal tails once complete.

# Coming updates 
The base infrastructure of the method is now complete. It appears I've succeeded in capturing the presence of a tail extending in the -y direction of the galactic coordinate system. All that is left it too fine tune paramaters such as the size of the partitions, define what velocities are charactersitic of stars within extended tidal radiii and tidal tails, and the intial data to feed through the algorithm.  



