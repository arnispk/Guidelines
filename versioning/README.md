# Versioning
Netwerven's semantic versioning logic must follow all rules that are described below.

## Version numbers
1. Given a version number MAJOR.MINOR.PATCH, increment the:
  - MAJOR version when incompatible changes have been made,
  - MINOR version when functionality has been added in a backwards-compatible manner
  - PATCH version for backwards-compatible bug fixes.
  
2. Major version 0 (0.x.y) only addresses development releases and may be used for tracking progress
internally.
  
3. Version 1.0.0 denotes the release of the public website.

4. Patch version Z (x.y.Z where x > 0) must be incremented whenever a bugfix has been issued

5. Minor version Y (x.Y.z where x > 0) must be incremented whenever new functionality (feature) or an 
improvement/enhancement has been added. A minor version increment resets the patch version (z) to 0.

6. Major version X (X.y.z | X > 0) must be incremented when non-backwards compatible changes 
have been introduced (e.g. an overhaul of a website's interface). The minor version (y) as well as the 
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

A major version surpasses any minor versions and patch versions. So, a major version with two extra functional additions as well as four bug fixes, considering the same aformentioned public version number, doesn't result in version 2.3.4, but results in version 2.0.0.

A release is initially pushed to an acceptance or staging server. The postfix '-RCn' (where 'RC' stands for **R**elease **C**andidate and '**n**' is the release candidate incremental change counter) indicates that the release is a version ready to deploy, but isn't actually on production yet. 

Each change to the release candidate increments 'n'. So, the first RC for the major version 2.0.0 is 2.0.0-RC1. The second 2.0.0-RC2. The third 2.0.0-RC3 and so on. A push to production removes the '-RCn' postfix.

### Changelogs
Each release will have an accompanying changelog that lists all of the changes that have been made 
compared to the version before that.

A changelog:
- describes each change grouped per category:
  - added
  - removed
  - changed
  - fixed
  - deprecated
- links to corresponding tickets (ZenDesk, Redmine, Asana, Jira, ...)

<small>Source: [Mojombo server](https://github.com/mojombo/semver/blob/master/semver.md)</small>
 
