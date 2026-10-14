# f26-copy

Exact copy of the Fall 2026 dashboard (ben77g/f26-rhywl2wr) re-encrypted with a different password, made 2026-10-09 at the owner's request.
Same files (`index.html` lock screen + AES-256-GCM blob, `sw.js`, manifest, icons). Only the encryption salt/iv/ciphertext differ, and
the service-worker cache name is `fall2026-copy-v1` so it does not clash with the original.

- It is a snapshot of the original at commit 72b72b0. It does NOT update itself; the Tuesday/Thursday sync job only touches the original.
- To refresh it: decrypt the original with `~/agent/workspace/f26_dashboard_sync/build.sh decrypt`, then encrypt that plaintext with
  `tools/enc.mjs` (env `PW` = this copy's password) using a lock page from `tools/lock.py`, and commit `index.html`. Never commit the plaintext.
- The password is not stored in this repo.

- 2026-10-14: password changed at the owner's request (content unchanged: decrypted with the old password and re-encrypted with the new one; sw.js cache name bumped to `fall2026-copy-v2`). Old password no longer opens it.
