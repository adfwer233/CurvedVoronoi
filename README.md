# CurvedVoronoi
Voronoi diagram in spaces with constant curvature (plane, sphere or Poincare disk)

## Build
The rendering relies on the Vulkan, so if you want to build this project, please install Vulkan SDK.

```
git submodules update --init --recursive
mkdir build
cd build
cmake ..
cmake --build .

# Then find the target CurvedVoronoi and run it.
```

If you are using IDE like Clion, configure cmake and run the target `CurvedVoronoi`.

## Results

### Spherical Voronoi Diagrams
<p align="center">
  <img src="assets/spherical/16_convex.png" width="30%">
  <img src="assets/spherical/16_delaunay.png" width="30%">
  <img src="assets/spherical/16_voronoi.png" width="30%"><br>
  <small>16 Convex Hull</small>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <small>16 Delaunay Triangulation</small>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <small>16 Voronoi Diagram</small>
</p>
<p align="center">
  <img src="assets/spherical/64_convex.png" width="30%">
  <img src="assets/spherical/64_delaunay.png" width="30%">
  <img src="assets/spherical/64_voronoi.png" width="30%"><br>
  <small>64 Convex Hull</small>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <small>64 Delaunay Triangulation</small>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <small>64 Voronoi Diagram</small>
</p>
<p align="center">
  <img src="assets/spherical/1024_convex.png" width="30%">
  <img src="assets/spherical/1024_delaunay.png" width="30%">
  <img src="assets/spherical/1024_voronoi.png" width="30%"><br>
  <small>1024 Convex Hull</small>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <small>1024 Delaunay Triangulation</small>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <small>1024 Voronoi Diagram</small>
</p>

### Voronoi Diagram in Poincare Disk

<p align="center">
  <img src="assets/hyperbolic/64_e_complex.png" width="30%">
  <img src="assets/hyperbolic/64_h_complex.png" width="30%">
  <img src="assets/hyperbolic/64_voronoi.png" width="30%"><br>
  <small>64 Euclidean Delaunay</small>&nbsp;&nbsp;
  <small>64 Hyperbolic Delaunay</small>&nbsp;&nbsp;
  <small>64 Voronoi Diagram</small>
</p>
<p align="center">
  <img src="assets/hyperbolic/256_e_complex.png" width="30%">
  <img src="assets/hyperbolic/256_h_complex.png" width="30%">
  <img src="assets/hyperbolic/256_voronoi.png" width="30%"><br>
  <small>256 Euclidean Delaunay</small>&nbsp;&nbsp;
  <small>256 Hyperbolic Delaunay</small>&nbsp;&nbsp;
  <small>256 Voronoi Diagram</small>
</p>
<p align="center">
  <img src="assets/hyperbolic/2048_e_complex.png" width="30%">
  <img src="assets/hyperbolic/2048_h_complex.png" width="30%">
  <img src="assets/hyperbolic/2048_voronoi.png" width="30%"><br>
  <small>2048 Euclidean Delaunay</small>&nbsp;&nbsp;
  <small>2048 Hyperbolic Delaunay</small>&nbsp;&nbsp;
  <small>2048 Voronoi Diagram</small>
</p>

## Interactive UI

![](assets/ui.png)

## Reference

- [1] Manuel Caroli et al. “Robust and efficient Delaunay triangulations of points on or close to a
sphere”. In: Experimental Algorithms: 9th International Symposium, SEA 2010, Ischia Island,
Naples, Italy, May 20-22, 2010. Proceedings 9. Springer. 2010, pp. 462–473.
- [2] Olivier Devillers, Stefan Meiser, and Monique Teillaud. “The space of spheres, a geometric tool
to unify duality results on Voronoi diagrams”. PhD thesis. INRIA, 1992.
- [3] Mikhail Bogdanov, Olivier Devillers, and Monique Teillaud. “Hyperbolic Delaunay complexes
and Voronoi diagrams made practical”. In: Proceedings of the twenty-ninth Annual Symposium
on Computational Geometry. 2013, pp. 67–76.

## About

This project is finished in the Computational Geometry Course, Tsinghua University, 2025 Spring.

Authored by 
- Bao Anchang, School of Software
- Wang Jianyuan, Department of Computer Science and Technology