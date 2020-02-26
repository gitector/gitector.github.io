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


