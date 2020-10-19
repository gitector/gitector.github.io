## Check your commits not only code

Git history can be your source of truth. Same as with your code you need to take care of it.
Codebase linting is common practice but why neglect git history? How often you try to debug
Error and git blame is not helpful because of poor git message.

You can run gitector as part of your pre-commit check or CI pipeline.

## Gitector allows you to define rules for your commit

You can configure gitector in any way some of possible features include:

- Allow only commits with Ticket number
- Allow commiters with only certain email 
- Disallow merges 
- Define maximum characters for title
- Encourage small commits by limiting amount of files in single commit
- Make sure commit starts with action verb describing changes (like add, remove, fix)

### Compare all changes in your branch
[![asciicast](https://asciinema.org/a/295970.svg)](https://asciinema.org/a/295970)
### Use markdown formatter
[![asciicast](https://asciinema.org/a/295974.svg)](https://asciinema.org/a/295974)

## Usage

### CLI

Init gitector configuration with default settings

```bash
gitector init
```

Run gitector against your local branch and master branch

```bash
Gitector ..master
```

Get more support

```bash
gitector —-help
```

### Git hook

Edit file `.git/COMMIT_EDITMSG` and put inside
```bash
gitector -di
```

### Github Actions

You can find latest version to add to your [workflow here](https://github.com/gitector/gitector-actions)

### Gitlab

Add code below to your `.gitlab-ci.yml` file

```
gitector:
  stage: build
  image: gitector/gitector
  script:
    - git fetch
    - gitector
  except:
    - master

```


