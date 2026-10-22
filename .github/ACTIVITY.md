# Dark Hour Activity Log

The workflow `profile-3d.yml` generates a real GitHub contribution calendar using
the repository owner's username, not the display name in the banner.

- Push these changes to `main` to start the first generation, or select
  **Actions → Dark Hour Activity Log → Run workflow**.
- The included first-run SVG is only a placeholder. It contains no sample activity
  and is replaced by the first successful run.
- The calendar refreshes daily around 03:23 America/Sao_Paulo. Scheduled runs may
  be delayed by GitHub.
- Colors and animation are configured in `profile-3d-settings.json`.
- The workflow uses the automatic `GITHUB_TOKEN`; no personal token is required
  for public contributions. Enable Actions for the repository and allow this job
  to write repository contents. Branch rules must permit the generated commit.
- Contributions made only on a separate Gitea instance are not included.
- Profile repository: `EdwardFlammel/EdwardFlammel`. Keep it public and keep
  `README.md` at the root for GitHub to display it on your profile.

Generator and configuration reference:
https://github.com/yoshi389111/github-profile-3d-contrib
