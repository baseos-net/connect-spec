# Publish BaseOS Connect

Do this after the four GitHub repositories exist and are empty. Run the commands on your machine. Nothing here pushes or publishes by itself.

npm organization that exists: https://www.npmjs.com/settings/baseos/packages
Package scope: `@baseos/connect-node`

## 1. Repositories

From the monorepo, each directory below becomes one repository. Default branch `main`.

| Local directory | GitHub repository |
|---|---|
| `baseos/packages/baseos-connect/github-org` | `baseos-net/.github` |
| `baseos/packages/baseos-connect/protocol` | `baseos-net/connect-spec` |
| `baseos/packages/baseos-connect/laravel` | `baseos-net/connect-laravel` |
| `baseos/packages/baseos-connect/node` | `baseos-net/connect-node` |
| `baseos/packages/baseos-connect/docs` | `baseos-net/docs` |

`connect-cli` stays inside `connect-node`. The `baseos-connect` bin is that package.

WordPress stays in BaseOS Core. Do not put Core in these repositories.

## 2. Push

Run inside each directory after `git init`. Replace the remote if you use HTTPS.

```bash
git init
git add .
git commit -m "Publish BaseOS Connect."
git branch -M main
git remote add origin git@github.com:baseos-net/REPO.git
git push -u origin main
```

`REPO` is `.github`, `connect-spec`, `connect-laravel`, `connect-node`, or `docs`.
The `.github` remote is `git@github.com:baseos-net/.github.git`.

## 3. Packagist

Submit only after `connect-laravel` is on GitHub and `composer validate` passes in that repository.

https://github.com/baseos-net/connect-laravel

Confirm the package name is `baseos/connect-laravel`. Turn on the GitHub update webhook.

## 4. npm

In the npm organization `baseos`, add this GitHub repository as a trusted publisher for `@baseos/connect-node` before the first tag, or publish once from the `connect-node` directory:

```bash
npm login
npm publish --access public
```

The workflow `.github/workflows/publish.yml` publishes on tags `v*` after trusted publishing is configured. It does not run on a normal push.

## 5. After the first publish

Point https://baseos.net/connect at the docs repository, or render that README there. Installed sites keep calling `/api/v1/connect` and `/baseos`.
