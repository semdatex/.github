# GitHub Community Health Files

## What is this?

This is a special repository that GitHub users to apply default community health files to all repositories in an organization.

More info here: https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file

## Why do we need a default template repository?

Have a single source of truth for our pull-request templates.

## How is this used?

https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates

## Why some repositories also carry their own copy

The default template here only populates the PR form in the web UI. It is not in any
repository's working tree, so a PR opened through the API — by a bot, an agent, or
`gh pr create --body` — never sees it, and gets no structure at all.

Repositories that need the structure to hold for API-created PRs therefore commit their
own `.github/pull_request_template.md`. Today that is `infrastructure-root`,
`more-platform` and `marketing-website`; each also runs an advisory
`PR Description Lint` check that derives its legal section set from that committed copy,
so the template and the check cannot drift apart.

**Keep the section headings here and in those copies identical.** Everything else in
this file (the guidance comments) may differ. Every other repository in the org still
falls back to this template.
