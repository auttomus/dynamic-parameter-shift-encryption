# Dynamic Parameter Shift Encryption (DPSE)

This project implements a novel encryption method called Dynamic Parameter Shift Encryption (DPSE), inspired by the classic Caesar Cipher but significantly enhanced with multiple dynamic parameters to increase complexity and security.

## Overview

DPSE utilizes three dynamic parameters that shift and transform characters based on their position within the message. This multi-parameter approach ensures that each character's encryption is unique, making it more robust than traditional single-parameter ciphers.

## Features

- **Dynamic Zero Index (Karakter Index 0)**: A variable starting point for character mapping, which can be a single character for the entire message or a sequence of characters applied cyclically.
- **Dynamic Shift Value (Bilangan Shift P)**: A variable integer value that determines the magnitude of the shift for each character. This can also be a single value or a sequence of integers.
- **Dynamic Operator Pattern (Pola Operator r)**: A sequence of '+' or '-' operators that dictate whether the shift is an addition or subtraction, applied cyclically.
- **Comprehensive Character Set**: Supports encryption and decryption of alphanumeric characters (0-9, A-Z, a-z).
- **Complexity Analysis**: The encryption interface provides a real-time analysis of the encryption's complexity and security rating based on the parameters used.
- **Step-by-Step Calculation Details**: Both encryption and decryption processes offer detailed breakdowns of how each character is transformed, aiding in understanding and verification.

## How it Works

### Encryption (`Encryption.html`)

1.  **Input Message**: The original text to be encrypted.
2.  **Parameter Configuration**: Users input the Zero Index, Shift Value (P), and Operator Pattern (r). These can be single values or comma-separated sequences.
3.  **Character Processing**: Each character in the message that is part of the defined `sequence` (0-9, A-Z, a-z) is processed individually.
    -   The `zeroChar` (from Zero Index), `integer` (from Shift Value), and `operator` (from Operator Pattern) are applied cyclically based on the character's position.
    -   The character's relative position to its `zeroChar` is calculated.
    -   A `zeroInfluence` (quadratic based on `zeroChar`'s position) is applied.
    -   The shift operation (addition or subtraction) is performed using the `integer` and `operator`.
    -   The final encrypted character is derived.
4.  **Output**: The encrypted message and a detailed calculation log for each character.

### Decryption (`Decryption.html`)

1.  **Input Encrypted Message and Parameters**: To decrypt, the exact encrypted message and the original Zero Index, Shift Value, and Operator Pattern used during encryption are required.
2.  **Reverse Character Processing**: For each encrypted character:
    -   The `zeroChar`, `integer`, and `operator` are applied cyclically, mirroring the encryption process.
    -   The `zeroInfluence` is removed.
    -   The shift operation is reversed (e.g., if '+' was used for encryption, '-' is used for decryption).
    -   The original character is recovered.
3.  **Output**: The decrypted original message and a step-by-step explanation of the decryption process.

## Usage

To use the DPSE calculator:

1.  Open `Encryption.html` in your web browser to encrypt messages.
2.  Open `Decryption.html` in your web browser to decrypt messages. Ensure you have the correct encryption parameters (Zero Index, Shift Value, Operator Pattern) used during encryption.

## Development

The project is built using HTML, CSS, and JavaScript, making it a client-side application. No backend server is required.

### Files:
-   `Encryption.html`: Contains the interface and logic for encrypting messages.
-   `Decryption.html`: Contains the interface and logic for decrypting messages.
-   `README.md`: This file, providing an overview of the project.
-   `LICENSE`: The license file for the project.
-   `.gitattributes`: Git configuration file.

## License

This project is licensed under the [MIT License](LICENSE).
