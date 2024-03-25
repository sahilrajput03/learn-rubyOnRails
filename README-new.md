# Running your github pages site locally with jekyll

Sources:
- AWESOME (*this finally helped*): [Click here](https://github.com/orgs/community/discussions/37669#discussioncomment-4079487)
- Docs - Testing your GitHub Pages site locally with Jekyll: [Click here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)
	- Docs - Creating a GitHub Pages site with Jekyll: [Click here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)
- Jekyll docs: [Click here](https://jekyllrb.com/docs/)
	- Above docs suggested the additional install of `webrick` by running `bundle add webrick` which is necessary.
- Exclude folders from jekyll compilation, for e.g., `node_modules` - [Click here](https://talk.jekyllrb.com/t/can-i-exclude-files-in-my-project-folders-from-my-site/396)


# Steps:

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

`sudo bundle exec jekyll serve --livereload --incremental`

Thanks
