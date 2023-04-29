
GzipSwift
========================

[![platform](https://img.shields.io/badge/platform-macOS%20|%20iOS%20|%20watchOS%20|%20tvOS%20|%20Linux-blue.svg)]()
[![CI Status](https://github.com/1024jp/GzipSwift/workflows/CI/badge.svg)](https://github.com/1024jp/GzipSwift/actions)
[![SwiftPM-compatible](https://img.shields.io/badge/SwiftPM-✔-4BC51D.svg?style=flat)](https://swift.org/package-manager/)

__GzipSwift__ is a framework with an extension of Data written in Swift. It enables compress/decompress gzip using zlib.

- __Requirements__: OS X 10.9 / iOS 12 / watchOS 2 / tvOS 12 or later
- __Swift version__: Swift 5.6


## Usage

```swift
import Gzip

// gzip
let compressedData: Data = try! data.gzipped()
let optimizedData: Data = try! data.gzipped(level: .bestCompression)

// gunzip
let decompressedData: Data
if data.isGzipped {
    decompressedData = try! data.gunzipped()
} else {
    decompressedData = data
}
```


## Installation

### Swift Package Manager

GzipSwift is SwiftPM-compatible. To install, add this package to your `Package.swift` or your Xcode project.

#### For Linux

1. Install zlib if you haven't installed yet:

    ```bash
    $ apt-get install zlib-dev
    ```
2. Add this package to your package.swift.
3. If Swift build failed with a linker error:
    * check if libz.so is in your /usr/local/lib
        * if no, reinstall zlib as step (1)
        * if yes, link the library manually by passing '-Xlinker -L/usr/local/lib' with `swift build`


## License

© 2014-2023 1024jp

GzipSwift is distributed under the terms of the __MIT License__. See [LICENSE](LICENSE) for details.
