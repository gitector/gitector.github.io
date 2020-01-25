## Check your commits not only code

### Compare all changes in your branch
[![asciicast](https://asciinema.org/a/295970.svg)](https://asciinema.org/a/295970)
### Use markdown formatter
[![asciicast](https://asciinema.org/a/295974.svg)](https://asciinema.org/a/295974)

## Usage

### CLI

Edit file `.git/COMMIT_EDITMSG` and put inside
```bash
gitector -di
```

### Github Actions

### Gitlab

Add to your `gitlab-ci.yml`

```
stages:
  - gitector
  - build
  - deploy

gitector:
  image: gitector/gitector
  script:
    - git fetch
    - gitector
  only:
    refs:
      - merge_requests
      - master
      - web


```


