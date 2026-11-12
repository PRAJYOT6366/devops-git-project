# DevOps Git Workflow Demo

A tiny static site used to practice a clean Git workflow: `main`, `dev`, and feature branches, focused commits, pull requests, tags, and Markdown documentation. It has no build step or external dependencies.

## Run locally

Open `index.html` in any browser.

## Branch model

- `main`: stable, releasable work
- `dev`: integration branch for the next release
- `feature/<name>`: one focused change, branched from `dev`

## Typical contribution

1. `git switch dev` then `git pull origin dev`
2. `git switch -c feature/short-description`
3. Edit the project and review `git diff`.
4. `git add <files>` and `git commit -m "feat: describe the change"`.
5. `git push -u origin feature/short-description`.
6. Open a pull request on GitHub from the feature branch into `dev`. Review it, then merge it.
7. When `dev` is ready, open a pull request from `dev` into `main`, review, and merge.
8. Tag the release: `git switch main; git pull; git tag -a v1.0.0 -m "Release v1.0.0"; git push origin v1.0.0`.

Use pull requests on GitHub for shared work. The local history in this exercise demonstrates the same branch flow; it does not create a hosted pull request.

## Useful commands

```sh
git status --short --branch
git log --oneline --graph --decorate --all
git branch --list
git tag --list
git diff
```

## Customize Git identity

Before your first commit on a new computer, set your own identity:

```sh
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

For this generated demo, local commits use a generic placeholder identity. Replace it before publishing if you want your commits attributed to you.
