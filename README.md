<p align="center">
  <img width="250px" src="https://user-images.githubusercontent.com/13738772/201432652-63a10fc1-a6a5-423f-8ee0-b18a11308077.svg" />
<p align="center">


## Reset a Neon Branch 🚀
This GitHub action resets a Neon branch.

Here is an example of how to use it:

```yml
name: Reset Neon Branch with GitHub Actions Demo
run-name: Reset a Neon Branch 🚀
jobs:
  Reset-Neon-Branch:
    uses: neondatabase/reset-branch-action@beta
    with:
      project_id: rapid-haze-373089
      # optional (defaults to your primary branch)
      parent: true
      branch: from_action_reusable
      api_key: {{ secrets.NEON_API_KEY }}
    id: reset-branch
  - run: echo branch_id ${{ steps.reset-branch.outputs.branch_id }}
```

## Outputs
```yml
outputs:
  branch_id:
    description: 'New branch id'
    value: ${{ steps.create-branch.outputs.branch_id }}
```

## How to set up the NEON_API_KEY
Navigate to you the Account page on your Neon console. In the Developer Settings, Generate a new API key if you don't have one already.
It's important not to share the API key or expose it in your actions or code. This is why you need to add the API key to a new GitHub secret.

In your GitHub repo, go to `Settings` and locate `Secrets` at the bottom of the left sidebar. Click on `Actions` and then on the `New repository secret` button to create a new secret.
Name the secret `NEON_API_KEY` and paste the API key generated on the Neon console in the `Secret*` field, then press `Add secret` button.
