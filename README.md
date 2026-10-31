![Banner](banner.png)

# crypto-rate-limiter-bypass-tester
A local timing benchmark for HMAC, HKDF, signature, and AES operations. It generates its own keys and data, runs the selected operation locally for the requested number of iterations, and logs the total and average time. It sends no network requests and tests no rate limiter. - Focused on Basic cryptographic operations

## Install
`git clone https://github.com/ShadowStrikeHQ/crypto-rate-limiter-bypass-tester`

## Usage
`python3 main.py [params]`

Each operation is timed over the requested iterations and the average
is logged. The exit code is 0 when the selected operation completes
and 1 when it fails or the arguments cannot produce a run (iterations
below 1, an HKDF length below 1, or an AES key size other than 16, 24
or 32 bytes).

## Parameters
- `--operation`: The cryptographic operation to test (hmac, hkdf, signature, aes).
- `--iterations`: The number of iterations to perform.
- `--key_size`: The size of the key to use in bytes (default: 32).
- `--hkdf_length`: The length of the output for HKDF (default: 32).
- `--signature_algorithm`: The signature algorithm to use (ecdsa, rsa). Relevant for signature testing.
- `--aes_mode`: The AES mode of operation (cbc, ctr).  Relevant for AES testing

## License
Copyright (c) ShadowStrikeHQ
