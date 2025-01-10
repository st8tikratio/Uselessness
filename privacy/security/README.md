# Table of Contents

## Cybersecurity
- [Cybersecurity Sessions](/privacy/security/cyber-security-sessions.md)

# GPG Key Import
- [Yubikey](https://developers.yubico.com/PGP/Importing_keys.html)
  - Certain keys are fully compatible with RSA-4096; adjust above instructions accordingly
  - Check Yubikey RSA encryption capabilities - [here](https://www.yubico.com/ca/store/compare/)
  - Pre-requiites
    - GnuPG version 2.0.22 or later 
    - Yubikey’s OpenPGP module must be 1.0.5 or later
      ```
      Insert your YubiKey

      gpg-connect-agent --hex "scd apdu 00 f1 00 00" /bye
      ```
  
