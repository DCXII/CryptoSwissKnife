# CryptoSwissKnife

A comprehensive command-line interface (CLI) tool for various cryptographic operations. This project aims to provide a Swiss Army Knife for cryptography, offering a wide range of ciphers, hashing algorithms, key derivation functions, and more.

## Features

-   **Classical Ciphers**: Implementations of historical ciphers like Caesar, Vigenère, Playfair, etc.
-   **Modern Ciphers**: Support for AES, ChaCha20, Blowfish, and other contemporary encryption standards.
-   **Asymmetric Cryptography**: RSA, Diffie-Hellman, ECDH, ECDSA, and ElGamal.
-   **Post-Quantum Cryptography (PQC)**: Kyber, Dilithium, Falcon, and SPHINCS+.
-   **Homomorphic Encryption**: Paillier, BFV, and CKKS.
-   **Hashing Algorithms**: MD5, SHA-family, BLAKE2, and Tiger.
-   **Key Derivation Functions (KDF)**: bcrypt, scrypt, Argon2, PBKDF2, and HKDF.
-   **Steganography**: LSB image hiding/revealing.
-   **Quantum Cryptography**: BB84 QKD simulation.
-   **Blockchain & Cryptocurrency**: Simplified blockchain and wallet functionalities.

## Installation

To get CryptoSwissKnife up and running on your local machine, follow these steps:

### Prerequisites

*   **Python 3.8+**: Ensure you have a compatible version of Python installed.
    You can download it from [python.org](https://www.python.org/downloads/).
*   **pip**: Python's package installer, usually comes with Python.

### Steps

1.  **Clone the Repository**:
    First, clone the CryptoSwissKnife repository to your local machine using Git:
    ```bash
    git clone https://github.com/DCXII/CryptoSwissKnife.git
    cd CryptoSwissKnife
    ```

2.  **Set up a Virtual Environment** (Recommended):
    It's good practice to use a virtual environment to manage project dependencies.
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install Dependencies**:
    Install all required Python packages using pip:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

Once installed, you can launch the CryptoSwissKnife console and start exploring its features.

### Running the Console

To start the interactive console, run:
```bash
python3 run_console.py
```
You will be greeted by the CryptoSwissKnife banner and a `crypto >` prompt.

### Basic Commands

*   `help`: Displays a list of all available commands and their descriptions.
*   `show modules`: Lists all cryptographic modules available in the tool, categorized by type (e.g., `classical/caesar`, `modern/aes`).
*   `use <module_name>`: Selects a specific module to work with. For example:
    ```bash
    crypto > use classical/caesar
    crypto (caesar) >
    ```
*   `show options`: After selecting a module, this command shows the configurable options for that module.
*   `set <OPTION> <VALUE>`: Sets a value for a module option. For example:
    ```bash
    crypto (caesar) > set TEXT "Hello World"
    crypto (caesar) > set SHIFT 3
    crypto (caesar) > set MODE encrypt
    ```
*   `run`: Executes the selected module with the currently set options.
*   `back`: Deselects the current module, returning to the main `crypto >` prompt.
*   `exit` or `quit`: Exits the CryptoSwissKnife console.

### Example: Encrypting with Caesar Cipher

1.  **Start the console**:
    ```bash
    python3 run_console.py
    ```
2.  **Use the Caesar module**:
    ```bash
    crypto > use classical/caesar
    [+] Module 'classical/caesar' loaded
    crypto (caesar) >
    ```
3.  **Set options**:
    ```bash
    crypto (caesar) > set TEXT "GEMINI"
    [+] TEXT => GEMINI
    crypto (caesar) > set SHIFT 3
    [+] SHIFT => 3
    crypto (caesar) > set MODE encrypt
    [+] MODE => encrypt
    ```
4.  **Run the module**:
    ```bash
    crypto (caesar) > run
    [*] Running module...
    [+] Result: JHPLQL
    ```
5.  **Decrypt the message**:
    ```bash
    crypto (caesar) > set TEXT "JHPLQL"
    [+] TEXT => JHPLQL
    crypto (caesar) > set MODE decrypt
    [+] MODE => decrypt
    crypto (caesar) > run
    [*] Running module...
    [+] Result: GEMINI
    ```
6.  **Go back or exit**:
    ```bash
    crypto (caesar) > back
    [+] Module deselected
    crypto > exit
    [+] Thanks for using CryptoSwissKnife!
    ```

## Project Structure

The project is organized as follows:

*   `csk/`: Contains the core logic of the CryptoSwissKnife.
    *   `console.py`: Manages the interactive command-line interface.
    *   `engine.py`: Houses the implementations of various cryptographic algorithms.
    *   `utils.py`: Utility functions and classes (e.g., color formatting).
    *   `modules/`: A package containing individual module definitions for each cryptographic function. Each module inherits from `csk.modules.base.CryptoModule`.
*   `run_console.py`: The main entry point to start the CLI application.
*   `requirements.txt`: Lists all Python dependencies required for the project.
*   `tests/`: Contains unit tests for the cryptographic modules.
*   `venv/`: (Ignored by Git) The Python virtual environment.

## Contributing

We welcome contributions! Please see our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to submit issues, propose features, and make pull requests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
