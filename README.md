Pinterest Homebrew Tap
=====================

This is a [Homebrew][brew] tap for formulae for software developed by Pinterest


Setup
-----

Using these formulae requires Homebrew, which in turn requires Xcode. If you
have not yet installed Homebrew, a quick summary is at the end of this
document.

Once homebrew is installed, simply run:

    brew tap pinterest/tap

Use
---

To install software, just use `brew install` with the name of the formula. You
may wish to run `brew update` before hand to get the latest version of the
formulae. For example, to install the latest version of plank:

    brew update
    brew install plank

To upgrade software:

    brew update
    brew upgrade    # upgrade all software installed with Homebrew
    brew upgrade plank # update just the plank formula


Contributing
------------

Please file bug reports and feature requests as GitHub issues against the individual project, not this repository - however, we do accept pull requests here.

To do development on these formulae, first fork the repository on GitHub. Add
your fork as a remote to your local clone:

    cd $(brew --prefix)/Library/Taps/Pinterest/homebrew-tap
    git remote add me git@github.com:YOUR_GITHUB_USERNAME/homebrew-tap.git
    git fetch me

To propose changes, push to your fork (e.g. with `git push me +master`) and
submit pull request on GitHub.

We follow Homebrew's [standard coding style][style].

Appendix: overview of installing Homebrew
-----------------------------------------

The Homebrew developers suggest installing Homebrew at `/usr/local` to maximize
compatibility with existing software. To do so, follow the instructions on
[their website][brew].

This author prefers `/opt/homebrew`, finding that it works well enough in
practice and keeps a cleaner separation between other software which might use
`/usr/local`. To install at `/opt/homebrew`, you can use:

    sudo mkdir /opt/homebrew
    sudo chown `whoami` /opt/homebrew
    curl -sSLf -o homebrew-installer https://raw.githubusercontent.com/Homebrew/install/master/install
    perl -pi -e s,/usr/local,/opt/homebrew, homebrew-installer
    ruby homebrew-installer
    rm homebrew-installer
    echo '$PATH="/opt/homebrew/bin:/opt/homebrew/sbin:$PATH"' >> ~/.bashrc


References
----------
`brew help`, `man brew`, or the Homebrew [documentation][].

[brew]: http://brew.sh/
[style]: https://github.com/Homebrew/brew/blob/master/docs/Formula-Cookbook.md
[documentation]: https://github.com/Homebrew/brew/blob/master/docs/README.md
