# Contributing guidelines for meta repo

## Prerequisites

### Linux DCO / CLA

By contributing patches, you agree to the [Linux DCO] and sign-off your commits by adding
a `Singed-off-by` trailer on your commit message via `git commit --signoff`.

**For community contributors**: We do not require to sign our CLA in most projects (like this),
although if we adopt the Apache CLA (instead of rolling our own via Canonical's
[Project Harmony]), we'll assume your CLA signature will make your agreement to DCO legally
binding.

## Project-specific instructions

### Updating/adding team profiles

> **Note**: You should add your team profile in this repo and [not directly in wiki], due to how we setup CI for one-way synchorization.

For new members during onboarding, create your own team profile by [copying the template file] and fill in with your own.

```shell
# branch off if you have direct push access to the repo or fork to personal namespace
gh repo clone recaptime-dev/meta # with GitHub CLI
glab repo clone https://gitlab.com/recaptime-dev/squad/meta # with GitLab CLI
# option A: branch off (you can also branch off on your fork to keep things seperate
# from your own main branch)
git switch -c your-username/add-team-profile
# option B: fork via existing copy
gh repo fork recaptime-dev/squad --default-branch-only --remote
glab repo fork recaptime-dev/squad --remote

# first copy the template file into an new markdown file
cp team/template.md team/<your-github-username-in-lowercase>.md

# edit with your own details
$EDITOR team/<your-github-username-in-lowercase>.md

# make sure to protect your team profile file via CODEOWNERS
$EDITOR CODEOWNERS

# stage, sign-off and send a patch
git commit --signoff team/<your-github-username-in-lowercase>.md
git push origin your-username/add-team-profile
```

[Project Harmony]: https://en.wikipedia.org/wiki/Project_Harmony_(licensing)
[not directly in wiki]: https://wiki.recaptime.dev
[Linux DCO]: https://developercertificate.org/