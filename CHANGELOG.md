## 0.10.0 (01/17/2015)
* Partially implemented new conventions to reduce new allocations/increase performance (issue #23):
  * Operators will allocate new objects for clarity
  * Properties will normally allocate new objects (e.g. Vector2.normal)
  * All other functions will favor in-place versions where possible/practical
* Renamed scalarMultiply on vectors to just multiply for clarity.
* Added to Vector2: normalizeTo, clamp, divide, rotate (issue #29)
* Changed Frame3 to use a fully normalized quaternion inverse to avoid issues when inverting denormalized (e.g. interpolated) frames (issue #24).
* In-place quaternion inverse with normalization (issue #25).
* Fix for Quaternion clone doesn't clone its vector portion (issue #27).
* Fast inversion for frame matrices (frameMatrixInvert)
* Added Rect, the first of the geom structures.

## 0.8.0 (08/22/2014)
* Bugfix: Changed the cross product operator to '%' to avoid non-obvious precedence issues (Quaternion product was broken as a result).
* Added Frame3 for 3D transformations.

## 0.7.0 (08/20/2014)
* For core math structures: changed all underlying types to be static and removed default constructors. This is a huge performance gain for static targets like C++.
* Refactored coordinate frames to allow for implicit frames (adapters over existing sprites/entities with minimal overhead).

## 0.6.0 (08/12/2014)
* Bugfix: isDirty bit never set to false in Frame2 (matrix not being cached).

## 0.5.0 (08/11/2014)
* 2D coordinate frames have been added. They can be concatenated, inverted, used either to transform points/vectors directly or used as a way to generate OpenFL-compatible matrices. They provide a higher (and more useful) layer of abstraction than matrices along with an intuitive 'to/from' syntax describing whether the point/vector is being transformed into the frame from the outer frame, etc. A bug in the equality operators (throwing on null) has been fixed. Documentation has been added for all public members.

## 0.4.0 (08/07/2014)
* To/from conversion functions for FlxPoint/FlxVector (by shape; no dependency on Flixel).
* copyTo functions to preserve the other properties of target types/avoid allocating when undesired.

## 0.3.0 (08/02/2014)
* Signed and unsigned angle functions for 2D vectors.
* Array operator overloads for all structures.

## 0.2.0 (07/28/2014)
* Minor bugfixes, more test coverage.

## 0.1.0 (07/27/2014)
* Initial version. Basic functionality for vectors, matrices, and quaternions working.