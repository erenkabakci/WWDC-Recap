WWDC 2017

# Your apps and evolving network security * Tuesday 10:20
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/701/
_TLS -> Transport Layer Security_

# Best Practises
  - Update libraries
  - Update OS frequently
  - ATS enforces best practises

## Encryption
  - Do not use
    - RC4, CBC modes
  - Use
    - AES-GCM, ChaCha20/Poly1305
## Cryptographic Hashes
  - Do not use MD5, SHA-1
    - SHA-1 signed certificates are not supported by TLS anymore
  - Use SHA-2 family
## Public Keys
  - Do not use RSA key sizes `< 1024-bit RSA`
    - `< 2048-bit RSA` keys are not supported by TLS anymore
  - Use `> 2048-bit RSA`
## Protocols
  - Do not use,
    - `http://`
    - SSLv3
    - TLS 1.0, TLS 1.1
  - Use
    - `https://`
    - TLS 1.2
  - TLS 1.3
## Revocation
  - Do not do,
    - No checking
  - Use,
    - Certification Transparency
    - OCSP Stapling

# What to do now ?
  - Check your implementation, library & servers
  - Server devs,
    - Replace any SHA-1 certificates or weak RSA keys,
    - Upgrade servers to TLS 1.2 and authenticated encryption ciphers
    - Use OCSP Stapling
    - Check that your certificates are in CT logs
  - App devs,
    - Avoid ATS exceptions
