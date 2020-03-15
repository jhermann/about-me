# How I Built a GitHub Portfolio Site the Easy Way

*Tags:* github · jekyll · showdev

> *Quickly create a personal website that showcases your work as a software developer.*

![Cover Image](https://dev-to-uploads.s3.amazonaws.com/i/kdn9nc503g9fow5bcou0.png)

This is a quick summary of how I built https://jhermann.github.io/about-me/ using GitHub's `personal-website` Jekyll template. You can see the end result at that URL, or in the article's cover image, with a dark style applied.

## Initial Setup

After forking the [personal-website](https://github.com/github/personal-website) template repository, I cloned it to my disk and installed a local copy of Jekyll.

For that, I called these commands in my working directory, installing everything into my home directory:

    gem install --user-install jekyll bundler
    bundle config set path "$(ruby -r rubygems -e 'puts Gem.user_dir')"
    bundle install

Next I started the local web server like so:

    bundle exec jekyll serve

The server is then available at `http://localhost:4000`. For many changes, e.g. styling and layout ones, that server will rebuild the site almost instantly. However, some changes e.g. to `_config.yml` will require a full restart by pressing Ctrl-C and repeating the above command.

## Making the Template Site My Own

Some of the data in the sidebar, including the avatar, was fetched from my GitHub account data. To complete the sidebar, I added social accounts to the configuration, as described in the README.

The content on the right side has two sections.

* The *project list* is also fetched from the API, I just had to set the `stars` sort order, define a limit on the number of cards, and filter conditions to hide some repositories.
* The *list of interests / topics* I changed via the configuration, with a name, URL, and image for each entry. I created the images myself using `InkScape`, so they nicely fit together.

Every time I push a change I previewed locally, the site gets rebuilt by GitHub. I had to enable that in “Settings › Options › GitHub Pages”, setting the source to the `master` branch.

For more customization, the [Jekyll docs](https://jekyllrb.com/docs/) cover all the details not mentioned in the README.
