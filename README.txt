D-nide Vault - prototype source

Main file:  D-nide Vault.dc.html  (all screens + app logic)
Also needed: support.js (runtime), android-frame.jsx (phone frame),
             _ds/ (Broadsheet design system), fonts/phosphor-duotone/ (icons)

To run locally, serve this folder over HTTP rather than double-clicking:
  python3 -m http.server 8000
then open http://localhost:8000/D-nide%20Vault.dc.html
(React and Babel load from unpkg.com, so an internet connection is needed.)

Encryption
  Master password -> Argon2id (64 MiB, 3 passes, random salt) -> 256-bit key
  Vault and backup files -> AES-256-GCM, fresh random IV on every save
  The master password and key are never stored; the key is dropped on lock.
  Encrypted vault is kept in the browser's IndexedDB.
  vendor/argon2.umd.min.js is hash-wasm 4.13.0 (MIT, see vendor/hash-wasm-LICENSE).
  Passphrase words: EFF long wordlist (CC BY 3.0).
