### Platform-individual meta specification ``platform_attributes``
Dart package to describe native platforms with generic attributes.
Allows for individual member fields for different platforms with a
single implementation root.

````dart
void pltattrs() => Platform.windows(architecture: .X64, buildVersion: .win11_24H2);
void ownVersion() => Platform.windows(architecture: .ARM, buildVersion: WindowsBuildVersion(buildNumber, semanticVersion));
````
The package is just about the representation. The only logic is for parsing and constructing.

Use like this.

````dart
bool testApple() => Platform.current().os == .macos && 
    Platform.current().attributes.arch.arch == .aarch64;
````

It isn't more than this.