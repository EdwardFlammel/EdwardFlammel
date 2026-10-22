# Dark Hour Activity Log

The workflow [profile-3d.yml](workflows/profile-3d.yml) generates the contribution
calendar for the repository owner using real GitHub activity.

## Updates

- The calendar is stored in `profile-3d-contrib/mitsuru.svg` and is already generated.
- It refreshes daily around 03:23 America/Sao_Paulo (06:23 UTC). GitHub may delay
  scheduled runs.
- Changes to the README, workflow or color configuration also trigger a refresh
  when pushed to `main`.
- To refresh manually, open **Actions → Dark Hour Activity Log → Run workflow**.
- Colors and animation are configured in
  [profile-3d-settings.json](profile-3d-settings.json).

## Permissions and visibility

- The job uses the automatic `GITHUB_TOKEN` with `contents: write` to commit only
  the generated calendar. No personal token is required for public contributions.
- Actions must be enabled and branch rules must allow the generated commit.
- Activity made only on a separate Gitea instance is not included.
- The profile repository is `EdwardFlammel/EdwardFlammel`. It must be public, with
  `README.md` at the root, for GitHub to display the README on the profile page.

## Banner maintenance

- `assets/edward-mitsuru-clock.gif` is the animated banner used by the README.
- `assets/banner-source.svg` preserves the editable geometric artwork.
- The original MP4 is local only and is excluded by `.gitignore`.
- Artwork attribution and export details are in [CREDITS.md](../assets/CREDITS.md).

Generator: [GitHub Profile 3D Contrib](https://github.com/yoshi389111/github-profile-3d-contrib).
