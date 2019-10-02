Upgrading from Unity 2017.4 LTS to 2018.4 LTS
=============================================

Opt-In Test
-----------

You can opt-in to the 2018.4 LTS beta version from the Steam library:

1. Go to your Steam library
2. Find Unturned
3. Right click and select Properties
4. Switch to Betas tab
5. Choose "unity-2018" from dropdown

Known Issues
------------

Germany crashes when loaded. This should be fixed in a future LTS release: https://forum.unity.com/threads/having-a-crash-in-physicsmanager-simulate.735407/

Asset Bundles
-------------

There should not be any breaking changes (unlike 2017.4).

All backwards-compatibility is handled by the game. Individual .unity3d asset bundles as well as .masterbundles will have their shaders consolidated with new versions by the game. Custom shaders will need to be re-exported, at which point Asset_Bundle_Version can be set to 3 in MasterBundle.dat or individual .dat files.

All_Shaders.unitypackage has been updated for 2018.4 and now has a consistent export process to ensure the contents are kept valid.

Workshop
--------

Uploads from the beta will be incompatible with past versions of the game, and a patch will add a warning message to the 2017 version.

2017.4 Availability
-------------------
For archival purposes the 2017.4 version of the game will remain in a "unity-2017" beta branch.

Platforms
---------

Linux 32-bit and MacOS 32-bit have been removed, and of course 64-bit versions will always be available. Servers that were still using the outdated Linux 32-bit depot should update to the 64-bit Linux dedicated server.

Game Changes
------------

- Updated usage of OnApplicationQuit to new API.
- Updated usage of SplatPrototypes to TerrainLayers.
- Updated usage of WWW to UnityWebRequest.
- Optimized Steam thumbnail retrieval.
- Prevent duplicates in pending-load master bundles list.
- Assorted fixes to runtime-loaded UI textures.
- Various shader adjustments and fixes for new APIs.
- Fixed water audio on older maps with water disabled.
- Game volume is muted on loading screen by a new singleton responsible for master volume.
- Only game cameras own audio listeners now. Previously one was created for loading screens.
- Fixed shader consolidation for renderers with multiple shared materials.
- Workshop compatibility version incremented to 3.
- Master bundles use Asset_Bundle_Version now.
- Terrain neighbor connectivity is using groupingIDs because SetNeighbors is broken in this version.
- Scope UI alignment was slightly adjusted due to IMGUI changes.
- Usage of Unity analytics has been stripped. It was previously disabled, but now the module and references to it are compiled out.
- Stripped online server blacklist usage.
- Stripped splashscreen features.