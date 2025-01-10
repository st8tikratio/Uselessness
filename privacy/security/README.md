# Table of Contents

## Cybersecurity
- [Cybersecurity Sessions](/privacy/security/cyber-security-sessions.md)

# GPG Key Import
- [Yubikey](https://developers.yubico.com/PGP/Importing_keys.html)
  - Pre-requiites
    - GnuPG version 2.0.22 or later 
    - Yubikey’s OpenPGP module must be 1.0.5 or later
      ```
      Insert your YubiKey

      gpg-connect-agent --hex "scd apdu 00 f1 00 00" /bye
      ```
    - Check Yubikey RSA encryption level - [here](https://www.yubico.com/ca/store/compare/)
