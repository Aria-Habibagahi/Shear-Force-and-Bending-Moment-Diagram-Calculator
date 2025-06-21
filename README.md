#  Shear-Force-and-Bending-Moment-Diagram-Calculator
Created: Summer 2025

#  Overview
A Python-based tool that models a statically determinate beam with one smooth-pin (hinge) support and one roller/rocker support. Users input beam length and load configurations , and the program computes support reactions, internal shear forces, and bending moments—then plots clear shear-force and bending-moment diagrams.
#  How the Code Runs-Setup and Instructions
1. User Input

-Prompts for beam span and support locations: pin at A, roller at B
-Asks for load configurations: point loads, point moments, UDLs, LDLs (magnitude & location)
-Stores inputs in arrays: pointLoads, pointMoments, distributedLoads, linearLoads

2. Initialization

-Creates reactions = [Va, Ha, Vb] (initially zeros)
-Initializes empty arrays: shearForce, bendingMoment

3. Compute Support Reactions

For each load type X ∈ {PL, PM, UDL, LDL}:
-reactions_X(n) reads the nth load, computes equivalent forces/moments, and solves for Va (and Ha, if applicable) and Vb
-Updates cumulative reactions and logs results in _record arrays

4. Generate Shear & Moment Diagrams

For each load type X:
-shear_moment_X(n) loops over beam positions X, combining effects from support reactions and that load
-Outputs Shear and Moment arrays for each individual load

5. Combine Results

-Appends each Shear and Moment array to shearForce and bendingMoment, aggregating diagram data across all loads

6. Output Reactions & Plot Diagrams

-Prints final support reactions: Va, Ha, and Vb
-Plots the shear force and bending moment diagrams using Matplotlib, with clear labels for easy interpretation

# Future Improvements
-Support multi-span beams, more complex loadings, and intermediate supports
-Include additional support types: fixed, cantilever, or propped supports
-Extend to 3D beam structures and visualizations in multiple orientations
-Add support for Built-In, Guided, etc., and allow loading in different spatial orientations
