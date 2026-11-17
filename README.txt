D-nide Vault - prototype source

Main file:  D-nide Vault.dc.html  (all screens + app logic)
Also needed: support.js (runtime), android-frame.jsx (phone frame),
             _ds/ (Broadsheet design system), fonts/phosphor-duotone/ (icons)

To run locally, serve this folder over HTTP rather than double-clicking:
  python3 -m http.server 8000
then open http://localhost:8000/D-nide%20Vault.dc.html
(React and Babel load from unpkg.com, so an internet connection is needed.)
