# Swiss QR Bill Integration Project

This project implements Swiss QR Bill generation for invoices according to the Swiss Payment Standards (SPS).

## About Swiss QR Bills

The Swiss QR bill is a standardized payment slip with an embedded QR code that complies with the Swiss Payment Standards. It has been mandatory for businesses in Switzerland since 2020, replacing the traditional orange payment slips.

## Implementation Options

This project provides multiple implementation options for generating Swiss QR bills:

1. **Native JavaScript/TypeScript Implementation**  
   Uses `qrcode.react` to generate QR codes with the correct Swiss QR content format.

2. **QRInvoice C++ Integration**  
   Uses the [qrinvoice-cpp](https://bitbucket.org/codeblockgmbh/qrinvoice-cpp.git) library compiled to WebAssembly.

## Setup Instructions

### Prerequisites

- Node.js 16+
- For WebAssembly compilation (optional):
  - Emscripten SDK
  - CMake

### Installation

1. Install dependencies:
   ```
   npm install
   ```

2. (Optional) Fetch and build the qrinvoice-cpp library:
   ```
   npm run fetch-qrinvoice
   ```

3. Start the development server:
   ```
   npm run dev
   ```

## Implementation Details

The Swiss QR Bill implementation follows these standards:

- QR code size: 46mm × 46mm
- Swiss cross in the center: 7mm × 7mm
- Using QR code version 2.0 specification
- Properly formatted payment data according to SPS

## Troubleshooting

If the QR code isn't recognized by banking apps:

1. Make sure the IBAN format is correct
2. Check that the QR code data format follows the Swiss Payment Standards
3. Try different Reference Type formats (NON, QRR, or SCOR)
4. Generate a PDF and print at 100% scale to test with physical banking apps

## Resources

- [Swiss Payment Standards](https://www.paymentstandards.ch/en/home/softw/documentation.html)
- [QR-bill implementation guidelines](https://www.paymentstandards.ch/dam/downloads/ig-qr-bill-en.pdf)