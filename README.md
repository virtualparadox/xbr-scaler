# GoLang xBR Scaler

GoLang xBR Scaler is a Go implementation of the xBR scaling algorithm, 
originally developed in JavaScript ([xBRjs by joseprio](https://github.com/joseprio/xBRjs/blob/master/src/index.js)). This project aims 
to provide an efficient and easy-to-use solution for scaling pixel art 
images in GoLang applications, preserving the artistic style and enhancing 
the quality of low-resolution images.

## Features

- 2x, 3x, and 4x scaling using the xBR algorithm.
- Options for color blending and alpha scaling.
- Original and alternative xBR algorithm implementations.

## Installation

To use the GoLang xBR Scaler in your project, you can install it using `go get`:

## Usage

### PNG Scaler Util
```go
    pngScaler := NewPngScaler(true, true, false) // blend colors, scale alpha, do not use original 3x impl
    pngScaler.ScalePng("input.png", "output.png", 4) // read input.png and write 4x output to output.png
```

### XBR Scaler
```go
package main

import (
    "github.com/virtualparadox/xbrscaler"
)

func main() {
    // Load your pixel data into pixelArray (slice of uint32)
    pixelArray := []uint32{/* your pixel data */}
    originalWidth, originalHeight := /* your image dimensions */

    // Create a new Xbr scaler instance
    scaler := xbr.NewXbrScaler(false) // do not use original 3x scaling implementation

    // Scale the image using 2x scaling
    scaledPixels, scaledWidth, scaledHeight := scaler.Xbr3x(&pixelArray, originalWidth, originalHeight, true, true)

    // scaledPixels now contains the scaled image data
    // scaledWidth and scaledHeight are the dimensions of the scaled image
}
```

## Examples
| Original | 3x Zoom |
|----------|---------|
| ![Original Image](URL_to_original_image) | ![Zoomed Image](URL_to_zoomed_image) |
| Description or details for original image | Description or details for zoomed image |


## Contributing
Contributions to the GoLang xBR Scaler are welcome! If you have improvements or bug fixes:

* Fork the repository.
* Create a new branch for your feature or fix.
* Implement your changes.
* Submit a pull request.
* Please ensure your code adheres to Go best practices and includes comments for GoDoc.

## License
This project is licensed under the MIT License.