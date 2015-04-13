# Versioning
Netwerven's semantic versioning logic must follow all rules that are described below.

## Version numbers
1. Given a version number MAJOR.MINOR.PATCH, increment the:
  - MAJOR version when incompatible changes have been made,
  - MINOR version when functionality has been added in a backwards-compatible manner, and
  - PATCH version for backwards-compatible bug fixes.
  
2. Major version 0 (0.x.y) only addresses development releases and may be used for tracking progress
internally.
  
3. Version 1.0.0 defines the public website.

4. Patch version Z (x.y.Z where x > 0) must be incremented whenever a bugfix has been issued

5. Minor version Y (x.Y.z where x > 0) must be incremented whenever new functionality (feature) or an 
improvement has been added. A minor version increment resets the patch version (z) to 0.

6. Major version X (X.y.z | X > 0) must be incremented when non-backwards compatible changes 
have been introduced (e.g. an overhaul of a website's interface. The minor version (y) as well as the 
patch version (z) have to be reset to 0.

## Releases
A release is a set of changes, enhancements and/or fixes that is meant to be pushed to a production 
environment. A release can contain:
- zero or one major version increments
- zero, one or more minor version increments and
- zero, one or more patch version increments
and leads to an increment of the version number.

For instance, an upcoming release that has two extra functional additions as well as four bug fixes, 
considering a public version number of 1.1.0, results in version 1.3.4.

### Changelogs
Each release will have an accompanying changelog that lists all of the changes that have been made 
compared to the version before that.

<small>Source: [Mojombo server](https://github.com/mojombo/semver/blob/master/semver.md)</small>
 
