# MultipleConfigurationsApp

This project is for reproducing a Cocoapods issue when specifying build configurations for a pod. Xcode project has three configurations: `Debug` (default), `Release` (default), and `Test` (added for this demo).

In `Podfile`, a configuration is specified:
```
pod 'SimulatorStatusMagic', '2.0', :configuration => 'Test'
```
or 
```
pod 'SimulatorStatusMagic', '2.0', :configurations => ['Test']
```

What happened: when building scheme with any non-`Test` configurations, `SimulatorStatusMagic` framework still appears in the build process.
Expected: `SimulatorStatusMagic` should not be built at all for non-`Test` configurations.
