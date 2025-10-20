# box2d-swift

Swift Package Manager wrapper for [Box2D](https://github.com/erincatto/box2d) v3.1.0.

## Requirements

- Swift 5.9+
- Xcode 15+ (for C++ interoperability)

## Installation

Add this package as a dependency in your `Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/soulfresh/box2d-swift", branch: "main")
]
```

Then add `box2d` to your target's dependencies:

```swift
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "box2d", package: "box2d-swift")
        ],
        swiftSettings: [
            .interoperabilityMode(.Cxx)
        ]
    )
]
```

## Usage

Import Box2D in your Swift code:

```swift
import box2d

// Create a world
var worldDef = b2DefaultWorldDef()
let worldId = b2CreateWorld(&worldDef)

// Add bodies, simulate, etc.
b2World_Step(worldId, 1.0/60.0, 4)

// Clean up
b2DestroyWorld(worldId)
```

## License

Box2D is developed by Erin Catto and licensed under the MIT license.
