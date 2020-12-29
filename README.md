# github-provider
Terraform github provider example of - how to create repository

## Pre-requirements
- [git](https://git-scm.com/downloads) need to be installed 
- [terraform](https://www.terraform.io/downloads.html) need to be installed
- [github account](https://github.com/) 

## How to consume

```bash
git clone git@github.com:base-line/github-provider.git
cd github-provider
terraform init
terraform apply
```

### Create github OAuth token

follow the [documentation](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token) how to create personal token. you can export it as ENV variable `export GITHUB_TOKEN=<API-TOKEN>`

## As result

you'll have git repository under your github account, check using `terraform show` the output should be similar

```bash
resource "github_repository" "example" {
    allow_merge_commit     = true
    allow_rebase_merge     = true
    allow_squash_merge     = true
    archived               = false
    default_branch         = "main"
    delete_branch_on_merge = false
    description            = "My awesome codebase"
    full_name              = "andrewpopa/example"
    git_clone_url          = "git://github.com/andrewpopa/example.git"
...
```

## Destroy

destroy created infrastructure if need be

```
terraform destroy
```