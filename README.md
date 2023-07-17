# blog

## Setup
### Prepration
1. Go to https://www.toptal.com/developers/gitignore/ and generate a file for
    1. macOS
    1. VisualStudioCode
    1. Hugo
1. Re-open the folder in a container
    1. Select `Golang`
    1. Select the latest version `1.20`
    1. Add `Hugo` feature
    1. Keep default

### Create the website
```bash
hugo new site blog
```

### Set up theme
```
cd blog
hugo mod init github.com/clement-fouque/blog

# Create the new config file
code config/_default/module.toml
```

Add the following content to the newly created file `module.toml`
```toml
[[imports]]
path = "github.com/jpanther/congo/v2"
```

Launch the site by executing `hugo server`. It'll download the different modules.

git submodule add https://github.com/jpanther/congo.git themes/congo