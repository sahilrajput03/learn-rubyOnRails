# Running your github pages site locally with jekyll

Sources:
- Jekyll on Docker (my dockerHelsinki's notes) with multi-stage build: [Click here](https://github.com/sahilrajput03/dockerHelsinki/blob/master/Part3/course-partt3/five/README.md#L12)
- Jekyll Template: https://github.com/topics/jekyll-theme
- AWESOME (*this finally helped*): [Click here](https://github.com/orgs/community/discussions/37669#discussioncomment-4079487)
- Docs - Testing your GitHub Pages site locally with Jekyll: [Click here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)
	- Docs - Creating a GitHub Pages site with Jekyll: [Click here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)
- Jekyll docs: [Click here](https://jekyllrb.com/docs/)
	- Above docs suggested the additional install of `webrick` by running `bundle add webrick` which is necessary.
- Exclude folders from jekyll compilation, for e.g., `node_modules` - [Click here](https://talk.jekyllrb.com/t/can-i-exclude-files-in-my-project-folders-from-my-site/396)

## Notes for MacOS (Dec 2024)

Installing ruby: Search for `Installing rvm` - [Learn MacOS](https://docs.google.com/document/d/1d4Tq28JC17lFqkoz3lqodACnOlCihFj-MnzNb2Vcqd8/edit?tab=t.0#heading=h.lds1iinfg4rk)

*Note*: You only need to use below commands (tested with ruby version `3.3.0`)

```bash
# install dependencies
bundle install

# run server
bundle exec jekyll serve --livereload --incremental

# to expose on internal ip address
bundle exec jekyll serve --livereload --incremental --host=0.0.0.0
```

## Notes for Archlinux (June 2024)

Versions (tested on archlinux): 

```bash
$ ruby --version
# OUTPUT:
# ruby 3.0.6p216 (2023-03-30 revision 23a532679b) [x86_64-linux]

$ bundler --version
# OUTPUT:
# Bundler version 2.5.6
```

Follow from this - [Guide to run Gihtub pages locally with Jekyll](https://github.com/orgs/community/discussions/37669#discussioncomment-4079487)

1. I had to do `sudo bundle install` using sudo otherwise I was getting permission error.

2. Make `Gemfile` contents to look like that:

```Gemfile
source "https://rubygems.org"
# Note to Sahil: 231 version specified below comes from this link - https://pages.github.com/versions/
gem "github-pages", "~> 231", group: :jekyll_plugins
gem "webrick", "~> 1.8"
```

3. Add any `node_modules` directory to `_config.yml` if you have any, otherwise ignore this step:

```yml
include: [".well-known"]
exclude: ["thoughts-principles-react/node_modules/*"]
```

4. run the serve command with --livereload, when using below command with `sudo` the devlopment server seems to work (otherwise I get permission error):

```bash
# run server
sudo bundle exec jekyll serve --livereload --incremental

# to expose on internal ip address
bundle exec jekyll serve --livereload --incremental --host=0.0.0.0
```
