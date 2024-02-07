<div style="text-align: center" align="center">
    <a href="https://recastnav.com"><img src="https://recastnav.s3.amazonaws.com/logo.png" /></a>
    <h3><b>Recast Navigation</b></h3>
    <i>State-of-the-art navmesh generation and navigation for games.</i><br />
    <a href="https://github.com/recastnavigation/recastnavigation/actions/workflows/Build.yaml"><img src="https://github.com/recastnavigation/recastnavigation/actions/workflows/Build.yaml/badge.svg"></a>
    <a href="https://github.com/recastnavigation/recastnavigation/actions/workflows/Tests.yaml"><img src="https://github.com/recastnavigation/recastnavigation/actions/workflows/Tests.yaml/badge.svg"></a>
</div>

![Recast Demo](/Docs/Images/screenshot.png)

## 🚀 Features

* 🤖 **Automatic** - Recast can generate a navmesh from any level geometry you throw at it
* 🏎️ **Fast** - swift turnaround times for level designers
* 🧘 **Flexible** - detailed customization options and modular design let you tailor functionality to your specific needs
* 🚫 **Dependency-Free** - building Recast & Detour only requires a C++98-compliant compiler
* 💪 **Industry Standard** - Recast powers AI navigation features in Unity, Unreal, Godot, O3DE and countless AAA and indie games and engines

Recast Navigation is divided into multiple modules, each contained in its own folder:

- `Recast/` - Navmesh generation
- `Detour/` - Runtime loading of navmesh data, pathfinding, navmesh queries 
- `DetourTileCache/` - Navmesh streaming.  Useful for large levels and open-world games
- `DetourCrowd/` - Agent movement, collision avoidance, and crowd simulation
- `DebugUtils/` - API for drawing debug visualizations of navigation data and behavior
- `Tess/` - Unit tests
- `RecastDemo/` - Standalone, comprehensive demo app showcasing all aspects of Recast & Detour's functionality

## ⚡ Getting Started

Check out [BuildingAndIntegrating.md](Docs/_2_BuildingAndIntegrating.md) for information on how to build the comprehensive RecastDemo project, as well as guidance on integrating Recast & Detour into your own project.

If you are new to Recast & Detour, check out [Sample_SoloMesh.cpp](/RecastDemo/Source/Sample_SoloMesh.cpp) in RecastDemo to get started with building navmeshes and [NavMeshTesterTool.cpp](/RecastDemo/Source/NavMeshTesterTool.cpp) for building paths with Detour.

## ⚙ How it Works

Recast constructs a navmesh through a multi-step mesh rasterization process. 

1. First Recast rasterizes the input triangle meshes into voxels.
2. Voxels in areas where agents would not be able to move are filtered and removed.
3. The walkable areas described by the voxel grid are then divided into sets of polygonal regions.
4. The navigation polygons are generated by re-triangulating the generated polygonal regions into a navmesh.

You can use Recast to build a single navmesh, or a tiled navmesh.
Single meshes are suitable for many simple, static cases and are easy to work with.
Tiled navmeshes are more complex to work with but better support larger, more dynamic environments.  Tiled meshes enable advance Detour features like re-baking, heirarchical path-planning, and navmesh data-streaming.

## 📚 Documentation & Links

Official documentation is available at [recastnav.com](https://recastnav.com)

Docs are generated via [Doxygen](https://www.doxygen.nl/) from source file comments and from markdown files in the `Docs/` directory.

- [Development Roadmap](Docs/_99_Roadmap.md)
- [Changelog](CHANGELOG.md)
- [Contribution Guidelines](CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Github](https://github.com/recastnavigation/recastnavigation)

## ❤ Community

Ask questions, voice ideas, or request new features over on [Github Discussions](https://github.com/recastnavigation/recastnavigation/discussions) or on our old [Google Group](http://groups.google.com/group/recastnavigation) list.

Check out the [Development Roadmap](Docs/_99_Roadmap.md) to see what features and functionality you might be able to help with, and the [Contribution Guidelines](CONTRIBUTING.md) for information on how to make contributions.

Our [Code of Conduct](CODE_OF_CONDUCT.md) applies to all Recast Navigation community channels.

## ⚖ License

Recast & Detour is licensed under the ZLib license. See [License.txt](License.txt) for more.