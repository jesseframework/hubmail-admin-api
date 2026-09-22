# HubMail fork of grommunio admin-api

Branches:
- `master` is the HubMail distribution: grommunio's code plus our carried patches.
  The container build (jesseframework/hubmail-container) overlays this branch.
- `hubmail` is kept identical to `master`.
- Features meant for grommunio: branch off `upstream/master`, not our `master`, so
  the pull request doesn't include our patches.

Carried patches:
- Default license (no certificate uploaded) is `HubMail` with 100000 users instead of
  `Community` / 5. Override in a config.yaml / conf.d file:

      options:
        defaultLicenseUsers: 100000
        defaultLicenseProduct: HubMail

  An uploaded signed license certificate still takes precedence.

Sync with upstream:

    git fetch upstream
    git checkout master && git merge upstream/master && git push origin master
    git checkout hubmail && git merge --ff-only master && git push origin hubmail

This is AGPL-3.0 software: the modified source we run for users stays public here.
