---
layout: post
title: "New in CGAL: Polygonal Surface Reconstruction"
description: "Introducing a new package piecewise planar object reconstruction from point clouds"
category:
tags: [""]
---
{% include JB/setup %}

<h3><a href="https://3d.bk.tudelft.nl/liangliang/">Liangliang Nan</a></h3>
<h4><a href="https://www.tudelft.nl/en/">Delft University of Technology</a></h4>

<br>
<p>Reconstructing 3D models of piecewise planar objects from sampled points has been a major problem in both computer vision and computer graphics. Although it has been extensively researched in the past few decades, obtaining faithful reconstructions of real-world objects from unavoidably noisy and possibly incomplete point clouds remains an open problem. CGAL already offers a few surface reconstruction methods, such as
<a href="https://cgal.geometryfactory.com/CGAL/doc/master/Poisson_surface_reconstruction_3/index.html#Chapter_Poisson_Surface_Reconstruction">Poisson Surface Reconstruction</a>,
<a href="https://cgal.geometryfactory.com/CGAL/doc/master/Advancing_front_surface_reconstruction/index.html#Chapter_Advancing_Front_Surface_Reconstruction">Advancing Front Surface Reconstruction</a>, and
<a href="https://cgal.geometryfactory.com/CGAL/doc/master/Scale_space_reconstruction_3/index.html#Chapter_Scale_space_reconstruction">Scale-Space Surface Reconstruction</a>.</p>

<p>These methods are particularly suitable for point sets representing objects described by smooth surfaces. However, for man-made objects such as buildings, the results might not be satisfactory due to the imperfections and complexity of the reconstructed models (for example, gigantic meshes, missing regions, noises, and undesired structures). This is mainly because these methods tend to closely follow the surface details.</p>

<br>
<h3> Polygonal Surface Reconstruction</h3>

<p>This package implements a hypothesis-and-selection based method for piecewise planar object reconstruction from point clouds, originally described in 
<a href="https://3d.bk.tudelft.nl/liangliang/publications/2017/polyfit/polyfit.html">Nan and Wonka 2017</a> in the <a href="http://iccv2017.thecvf.com/">International Conference on Computer Vision (ICCV)</a>. The method takes as input an unordered point set sampled from a piecewise planar object and outputs a simplified and watertight surface mesh interpolating the input point set.</p>

<br>
<div style="text-align:center;">
  <img src="../../../../images/polyfit_pipeline.png" width="100%"><br>
  <small> Polygonal surface reconstruction: (a) Input point set; (b) Extracted planar segments; (c) Candidate faces are generated by pairwise intersection; (d) Faces selected through optimization; (e) Reconstructed model.</small>
</div>

<br>
<p>The method assumes that all necessary major planes are provided (for example using the new tools in the Shape detection package, see also <a href="../../07/30/Shape_detection">this post</a>), or they can be extracted from the input point set). It can recover sharp features of the objects, and it can handle a large amount of noise and outliers, complementing the existing surface reconstruction methods.</p>

<br>
<p>This package is already available in CGAL's master branch
on the <a href="https://github.com/CGAL/cgal/">CGAL GitHub repository</a>,
and will be officially released in the upcoming version of CGAL, 5.0, scheduled for Autumn 2019.</p>

<i class="glyphicon glyphicon-book"></i>
<a href="https://cgal.geometryfactory.com/CGAL/doc/master/Polygonal_surface_reconstruction/index.html#Chapter_PolygonalSurfaceReconstruction">Documentation of the package Polygonal_surface_reconstruction</a> <br>

<i class="glyphicon glyphicon-download"></i>
<a href="https://github.com/CGAL/cgal/tree/master">CGAL master branch on GitHub</a>