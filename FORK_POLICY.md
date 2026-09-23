# Fork maintenance policy

This is the controlled source for the Radio Atlas plugin installed on this
account's Omarchy machines. It is intentionally not kept automatically in
sync with `AksharP5/omarchy-radio-atlas`.

The initial code review covered upstream commit
`1a2d7edd2ea0949344c49501c5e32e16f9ef25e5`. The repository test suite and
Omarchy plugin validation passed at that revision.

## Updating

Treat every upstream change as new third-party code:

1. Fetch the `upstream` remote without merging it.
2. Review the complete diff from the currently trusted revision.
3. Run `./tests/run` and `omarchy plugin validate .`.
4. Merge or cherry-pick the reviewed change and push it to this fork.
5. Explicitly run `omarchy plugin update akshar.radio-atlas` on each machine.

GitHub fork synchronization and unattended plugin updates should remain
disabled. The installed plugin's `origin` remote should point to this fork,
not directly to the upstream repository.
