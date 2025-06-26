# `swift-sentencepiece`

[![](https://img.shields.io/endpoint?url=https%3A%2F%2Fswiftpackageindex.com%2Fapi%2Fpackages%2Fjkrukowski%2Fswift-sentencepiece%2Fbadge%3Ftype%3Dswift-versions)](https://swiftpackageindex.com/jkrukowski/swift-sentencepiece)
[![](https://img.shields.io/endpoint?url=https%3A%2F%2Fswiftpackageindex.com%2Fapi%2Fpackages%2Fjkrukowski%2Fswift-sentencepiece%2Fbadge%3Ftype%3Dplatforms)](https://swiftpackageindex.com/jkrukowski/swift-sentencepiece)

Use [SentencePiece](https://github.com/google/sentencepiece) in Swift for tokenization and detokenization. It wraps `v0.2.0` of the original library.

## Installation

Add the following to your `Package.swift` file. In the package dependencies add:

```swift
dependencies: [
    .package(url: "https://github.com/jkrukowski/swift-sentencepiece", from: "0.0.3")
]
```

In the target dependencies add:

```swift
dependencies: [
    .product(name: "SentencepieceTokenizer", package: "swift-sentencepiece")
]
```

## Usage

### Encoding

```swift
import SentencepieceTokenizer

// load tokenizer from file
let tokenizer = try SentencepieceTokenizer(modelPath: "/path/to/sentencepiece.model")

// encode text
let encoded = tokenizer.encode("Hello, world!")
print(encoded)

// decode tokens
let decoded = tokenizer.decode([35378, 4, 8999, 38])
print(decoded)
```

## Command Line Demo

To run the command line demo, use the following command:

```bash
swift run sentencepiece-cli --model-path <model-path> [--text <text>]
```

Command line options:

```bash
--model-path <model-path>
--text <text>           (default: Hello, world!)
-h, --help              Show help information.
```

## Code Formatting

This project uses [swift-format](https://github.com/swiftlang/swift-format). To format the code run:

```bash
swift format . -i -r --configuration .swift-format
```

## Acknowledgements

This project wraps the original implementation [SentencePiece](https://github.com/google/sentencepiece)
