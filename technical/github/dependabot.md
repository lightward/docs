# Dependabot

## Secrets

We use environment variables and secrets pretty heavily. Dependabot _only_ gets to use these when responding to a `pull_request_target` event -- it's not a thing during `pull_request`. This is relevant, because some of our integration tests need to talk to a deployment environment.

{% hint style="warning" %}
Performing any automation on untrusted code is risky, and that's one way to describe what happens when we run tests on Dependabot pull requests. We use strictly separated environments to keep risk at an acceptable level.
{% endhint %}

## Automerge

This workflow sets up Dependabot pull requests for auto-merging via squash commit.

Note that it runs on `pull_request_target`. As with secrets, we use this event so that Dependabot qualifies for the necessary permissions.

{% code title=".github/workflows/dependabot.yml" %}
```yaml
name: Dependabot

on: pull_request_target

permissions:
  contents: write
  pull-requests: write

jobs:
  dependabot:
    name: Auto-merge
    if: github.actor == 'dependabot[bot]'
    runs-on: ubuntu-latest
    steps:
      - name: Dependabot metadata
        id: metadata
        uses: dependabot/fetch-metadata@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
      - name: Enable auto-merge
        run: gh pr merge --auto --squash "$PR_URL"
        env:
          PR_URL: ${{ github.event.pull_request.html_url }}
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
{% endcode %}

## Ruby repositories

Note that `BUNDLE_ENTERPRISE__CONTRIBSYS__COM` is defined as a Dependabot secret, at the organization level.

Note also that `registries` doesn't explicitly include rubygems.org. Don't love that, but rubygems.org appears to be included in practice anyway, so here we are.

Posting this largely so that anyone searching for Sidekiq Pro or Enterprise and Dependabot has something to find. :)

{% code title=".github/dependabot.yml" %}
```yaml
version: 2

registries:
  contribsys:
    type: rubygems-server
    url: https://enterprise.contribsys.com/
    token: ${{ secrets.BUNDLE_ENTERPRISE__CONTRIBSYS__COM }}

updates:
  - package-ecosystem: bundler
    directory: /
    registries:
      - contribsys
    schedule:
      interval: daily
    # appears to be required for this package manager to work at all
    insecure-external-code-execution: allow

  - package-ecosystem: docker
    directory: /
    schedule:
      interval: daily

  - package-ecosystem: github-actions
    directory: /
    schedule:
      interval: daily
```
{% endcode %}
