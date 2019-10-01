<p align="center">
  <img src="dotfiles.png" alt="Dotfiles Icon"/>
</p>

# Dotfiles

[![Circle CI Status](https://circleci.com/gh/bkuhlmann/dotfiles.svg?style=svg)](https://circleci.com/gh/bkuhlmann/dotfiles)

Shell scripts for applying default settings to UNIX-based operating systems.

By default, these are set to my preferences (namely for macOS) but you can change them to your
liking by editing any of the `*.tt` template files in the `home_files` directory. Read on to learn
more.

<!-- Tocer[start]: Auto-generated, don't remove. -->

## Table of Contents

  - [Features](#features)
  - [Screencast](#screencast)
  - [Requirements](#requirements)
  - [Setup](#setup)
  - [Upgrade](#upgrade)
  - [Usage](#usage)
    - [Aliases](#aliases)
      - [General](#general)
      - [Bash](#bash)
      - [Network](#network)
      - [Fuzzy Finder](#fuzzy-finder)
      - [tmux](#tmux)
      - [Homebrew](#homebrew)
      - [Git](#git)
      - [Tar](#tar)
      - [PostgreSQL](#postgresql)
      - [Redis](#redis)
      - [chruby](#chruby)
      - [Ruby](#ruby)
      - [Ruby Gems](#ruby-gems)
      - [Ruby Gems Whois](#ruby-gems-whois)
      - [Rake](#rake)
      - [Bundler](#bundler)
      - [Milestoner](#milestoner)
      - [Gemsmith](#gemsmith)
      - [RSpec](#rspec)
      - [Middleman](#middleman)
      - [Ruby on Rails](#ruby-on-rails)
      - [Crystal](#crystal)
      - [Elm](#elm)
      - [Rubocop](#rubocop)
      - [SimpleCov](#simplecov)
      - [Silver Surfer](#silver-surfer)
      - [direnv](#direnv)
      - [Yarn](#yarn)
      - [Z](#z)
      - [Path Finder](#path-finder)
      - [Sublime Text](#sublime-text)
      - [Marked 2](#marked-2)
      - [ASCII Doctor](#ascii-doctor)
      - [asciinema](#asciinema)
      - [duti](#duti)
      - [Terraform](#terraform)
      - [Watch](#watch)
    - [Functions](#functions)
      - [General](#general-1)
      - [less](#less)
      - [License Finder](#license-finder)
      - [OpenSSL](#openssl)
      - [curl](#curl)
      - [lsof](#lsof)
      - [Git](#git-1)
      - [GitHub](#github)
      - [PostgreSQL](#postgresql-1)
      - [Ruby](#ruby-1)
      - [Ruby Gems](#ruby-gems-1)
      - [Bundler](#bundler-1)
      - [Rake](#rake-1)
      - [Code Quality](#code-quality)
      - [RSpec](#rspec-1)
      - [Guard](#guard)
      - [Ruby on Rails](#ruby-on-rails-1)
      - [RailRoady](#railroady)
      - [Elm](#elm-1)
      - [asciinema](#asciinema-1)
      - [Overmind](#overmind)
      - [Dotfiles](#dotfiles)
    - [Git Hooks](#git-hooks)
    - [IRB, Pry, and Rails consoles](#irb-pry-and-rails-consoles)
    - [Pry Aliases](#pry-aliases)
  - [Versioning](#versioning)
  - [Code of Conduct](#code-of-conduct)
  - [Contributions](#contributions)
  - [License](#license)
  - [History](#history)
  - [Credits](#credits)

<!-- Tocer[finish]: Auto-generated, don't remove. -->

## Features

- Configures the Bash `.bashrc`, `.bash_profile`, and `.inputrc` files.
- Configures the `.hushlogin` file.
- Configures the [CTags](http://ctags.sourceforge.net) `.ctags` file.
- Configures the [Vim](http://www.vim.org) `.vimrc` file.
- Configures the [Git](http://git-scm.com) `.gitconfig`, `.gitignore`, and hook (i.e.
  `.git_template`) files.
- Configures the [Silver Surfer](https://github.com/ggreer/the_silver_searcher) `.agignore` file.
- Configures the [Ruby Gems](https://rubygems.org) `.gemrc` file.
- Configures the [Ruby](https://www.ruby-lang.org) `.ruby-version` and `.irbrc` files.
- Configures the [Pry](http://pry.github.com) `.pryrc` file.
- Configures the [Ruby Debugger](http://bashdb.sourceforge.net/ruby-debug.html) `.rdebugrc` file.
- Configures the [RSpec](http://rspec.info) `.rspec` file.
- Configures the [Awesome Print](https://github.com/michaeldv/awesome_print) `.aprc` file.
- Configures the [PostgreSQL](http://www.postgresql.org/docs/9.3/static/app-psql.html) `.psqlrc`
  file.
- Configures the [Rubocop](https://github.com/bbatsov/rubocop) `.rubocop.yml` file.
- Configures the [NPM](https://www.npmjs.org) `.npmrc` file.
- Configures [Sublime Text](http://www.sublimetext.com) as the default editor.
- Adds [Bash Completion](http://bash-completion.alioth.debian.org).
- Adds [GPG](https://www.gnupg.org) support.
- Adds [direnv](http://direnv.net) support.
- Adds [chruby](https://github.com/postmodern/chruby) support.
- Adds [Node.js](http://nodejs.org) support.
- Adds [Z](https://github.com/rupa/z) support.

## Screencast

[![asciicast](https://asciinema.org/a/263055.svg)](https://asciinema.org/a/263055)

## Requirements

- [macOS](https://github.com/bkuhlmann/mac_os)

## Setup

Open a terminal window and execute the following commands:

Current Version (stable)

    git clone https://github.com/bkuhlmann/dotfiles.git
    cd dotfiles
    git checkout 34.1.0

Master Version (unstable)

    git clone https://github.com/bkuhlmann/dotfiles.git
    cd dotfiles

Edit any of the `*.tt` (template) and/or `*.command` (command) files in the `home_files` directory
as you see fit. Then open a terminal window and execute the following command to install:

    cd dotfiles
    bin/run

Executing the `bin/run` script will present the following options:

    s: Show managed dotfiles.
    i: Install dotfiles (existing files are skipped).
    l: Link dotfiles to this project (interactive per file, excludes: env.sh and .gitconfig).
    c: Check for differences between $HOME files and this project's files.
    d: Delete dotfiles (interactive per file, excludes: env.sh and .gitconfig).
    q: Quit/Exit.

The options prompt can be skipped by passing the desired option directly to the `bin/run` script.
For example, executing `bin/run s` will show all managed dotfiles by this project.

After install, the following files will require manual updating:

- `.bash/env.sh`: Add secret/machine-specific environment settings (if any).
- `.gitconfig`: Uncomment the name, email, and token lines within the `[user]` and `[github]`
  sections to replace with your own details.

## Upgrade

When upgrading to a new version, run the following:

1. Run: `bin/run l`. Links new files. If not using linked files, run `bin/run d` and `bin/run i`
   instead.
1. Run: `bin/run c`. Displays file differences, if any. Usually, this will be excluded files.
1. Run: `exec $SHELL`. Updates current shell with the above changes.

## Usage

### Aliases

#### General

    .. = "cd .."
    ... = "cd ../.."
    cdb = "cd -"
    c = "clear"
    h = "history"
    l = "ls -alhT"
    o = "open"
    p = 'pwd | tr -d "\r\n" | _copy_and_print'
    du = "ncdu -e --color dark"
    l1 = "ls -A1 | _copy_and_print '\n'"
    cat = "bat --theme DarkNeon"
    man = "gem man --system"
    ping = "prettyping --nolegend"
    rmde = "find . -type d -empty -not -path '*.git*' -delete"
    top = "htop"

#### [Bash](https://www.gnu.org/software/bash)

    bashe = "$EDITOR $HOME/.config/bash/env.sh"
    bashs = "exec $SHELL"

#### Network

    sshe = "$EDITOR $HOME/.ssh/config"
    key = "open /Applications/Utilities/Keychain\ Access.app"
    ipa = 'curl --silent checkip.dyndns.org | ag --only-matching "[0-9\.]+" | _copy_and_print'
    dnsi = "scutil --dns"
    dnss = "sudo dscacheutil -statistics"
    dnsf = "sudo dscacheutil -flushcache && sudo killall -HUP mDNSResponder && printf 'DNS cache cleared.\n'"

#### [Fuzzy Finder](https://github.com/junegunn/fzf)

    ff = "fzf --preview 'bat --theme DarkNeon --color always {}'"

#### [tmux](http://tmux.sourceforge.net)

    tsl = "tmux list-sessions"
    tsa = "tmux attach-session -t"
    tsk = "tmux kill-session -t"
    tsr = "tmux rename-session -t"

#### [Homebrew](http://brew.sh)

    hb = "brew"
    hbi = "brew install"
    hbin = "brew info"
    hbu = "brew uninstall"
    hbl = "brew list"
    hbs = "brew search"
    hbsw = "brew switch"
    hbup = "brew update"
    hbug = "brew upgrade"
    hbp = "brew pin"
    hbpu = "brew unpin"
    hbd = "brew doctor"
    hbc = "brew cleanup"
    hbsu = "brew update && brew upgrade && brew cleanup"

#### [Git](http://git-scm.com)

    gi = "git init"
    gcle = "git config --local --edit"
    gcge = "git config --global --edit"
    gcd = "git config --show-origin"
    gget = "git config --get"
    gset = "git config --add"
    gst = "git status --short --branch"
    gl = 'git log --graph --pretty=format:"$(_git_log_line_format)"'
    glh = "_git_commit_last | _copy_and_print"
    glf = 'git fetch && git log --reverse --no-merges --pretty=format:"$(_git_log_line_format)" ..@{upstream}'
    glg = 'git log --pretty=format:"$(_git_log_line_format)" --grep'
    gls = 'git log --pretty=format:"$(_git_log_line_format)" -S'
    glt = 'git for-each-ref --sort=taggerdate --color --format = "%(color:yellow)%(refname:short)%(color:reset)|%(taggerdate:short)|%(color:blue)%(color:bold)%(*authorname)%(color:reset)|%(subject)" refs/tags | column -s"|" -t'
    grl = "git reflog"
    gg = "git grep"
    guthors = 'git log --color --pretty=format:"%C(bold blue)%an%C(reset)" | sort | uniq -c | sort --reverse'
    gd = "git diff"
    gdc = "git diff --cached"
    gdm = "git diff origin/master"
    gdw = "git diff --color-words"
    gdo = 'git diff --name-only | uniq | xargs $EDITOR'
    gdt = "git difftool"
    gdtc = "git difftool --cached"
    gdtm = "git difftool origin/master"
    glame = "git blame -M -C -C -C"
    gbi = "git bisect"
    gbis = "git bisect start"
    gbib = "git bisect bad"
    gbig = "git bisect good"
    gbir = "git bisect reset"
    gbisk = "git bisect skip"
    gbil = "git bisect log"
    gbire = "git bisect replay"
    gbiv = 'git bisect visualize --reverse --pretty=format:"$(_git_log_line_format)"'
    gbih = "git bisect help"
    gbt = "git show-branch --topics"
    gba = "git branch --all"
    gbn = "_git_branch_name | _copy_and_print"
    gm = "git merge"
    gcl = "git clone"
    gb = "git switch"
    gbb = "git switch -"
    gbm = "git switch master"
    ga = "git add"
    gau = "git add --update"
    gap = "git add --patch"
    gall = "git add --all ."
    gco = "git commit"
    gce = 'cat .git/COMMIT_EDITMSG | ag --invert-match "^\#.*" | pbcopy'
    gatch = "git commit --patch"
    gca = "git commit --all"
    gcm = "git commit --message"
    gcam = "git commit --all --message"
    gcf = "git commit --fixup"
    gcs = "git commit --squash"
    gamend = "git commit --amend"
    gamendh = "git commit --amend --no-edit"
    gamenda = "git commit --amend --all --no-edit"
    gcp = "git cherry-pick"
    gcpa = "git cherry-pick --abort"
    gcps = "git cherry-pick --skip"
    gashc = "git stash clear"
    gnl = "git notes list"
    gns = "git notes show"
    gna = "git notes add"
    gne = "git notes edit"
    gnd = "git notes remove"
    gnp = "git notes prune"
    gf = "git fetch"
    gpu = "git pull"
    gpuo = "git pull origin"
    gpuom = "git pull origin master"
    gpuum = "git pull upstream master"
    grbo = "git rebase --onto"
    grbc = "git rebase --continue"
    grbd = "git rebase --show-current-patch"
    grbs = "git rebase --skip"
    grba = "git rebase --abort"
    grbt = "git rebase --edit-todo"
    gr = "git restore"
    grr = "git rerere"
    gp = "git push"
    gpf = "git push --force-with-lease"
    gpn = "git push --no-verify"
    gpo = "git push --set-upstream origin"
    gpr = "git push review master"
    gps = "git push stage stage:master"
    gpp = "git push production production:master"
    gtag = "git tag"
    gtagv = "git tag --verify"
    gtags = "git push --tags"
    gwl = "git worktree list"
    gwp = "git worktree prune"
    ges = "git reset"
    grom = "git fetch --all && git reset --hard origin/master" # Reset local branch to origin/master branch. UNRECOVERABLE!
    gel = "git rm"
    gelc = "git rm --cached" # Removes previously tracked file from index after being added to gitignore.
    grev = "git revert --no-commit"
    glean = "git clean -d --force"

#### [Tar](http://www.gnu.org/software/tar/tar.html)

    bzc = "tar --use-compress-program=pigz --create --preserve-permissions --bzip2 --verbose --file"
    bzx = "tar --extract --bzip2 --verbose --file"

#### [PostgreSQL](http://www.postgresql.org)

    pgi = "initdb /usr/local/var/postgres"
    pgst = "pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start &"
    pgsp = "pg_ctl -D /usr/local/var/postgres stop -s -m fast"

#### [Redis](http://redis.io)

    reds = "redis-server /usr/local/etc/redis.conf &"
    redc = "redis-cli"

#### [chruby](https://github.com/postmodern/chruby)

    rb = "chruby"

#### [Ruby](https://www.ruby-lang.org)

    rbi = "ruby-install"

#### [Ruby Gems](https://rubygems.org)

    gemcr = "$EDITOR ~/.gem/credentials"
    geml = "gem list"
    gemi = "gem install"
    gemu = "gem uninstall"
    gemc = "gem cleanup"
    gems = "gem server"
    gemp = "gem pristine"
    geme = "gem environment"
    gemuc = "gem update --system && gem update && gem cleanup"
    gemcli = "ag --depth=1 --files-with-matches --file-search-regex gemspec executables | xargs basename | cut -d. -f1 | sort | _copy_and_print '\n'"

#### [Ruby Gems Whois](https://github.com/jnunemaker/gemwhois)

    gemw = "gem whois"

#### [Rake](https://github.com/ruby/rake)

    bert = "ber -T"
    berq = "ber code_quality"

#### [Bundler](http://bundler.io)

    ba = "bundle add"
    bb = "bundle binstubs"
    bs = "bundle show"
    bsp = "bundle show --paths"
    bi = "bundle install"
    bu = "bundle update"
    bo = "bundle outdated --only-explicit"
    bce = "$EDITOR $HOME/.bundle/config"
    bcon = "bundle console"
    be = "bundle exec"
    bch = "rm -f Gemfile.lock; bundle check"

#### [Milestoner](https://github.com/bkuhlmann/milestoner)

    ms = "milestoner"
    msc = 'milestoner --commits | _copy_and_print "\n"'
    msp = "milestoner --publish"
    mse = "milestoner --config --edit"

#### [Gemsmith](https://github.com/bkuhlmann/gemsmith)

    gsg = "gemsmith --generate"
    gse = "gemsmith --config --edit"
    gsr = "gemsmith --read"
    gso = "gemsmith --open"
    gsi = "rake install"
    gsp = "rake publish"
    gsq = "rake code_quality"

#### [RSpec](http://rspec.info)

    rss = "rspec spec"
    rst = "rspec spec --tag"
    rsn = "rspec spec --next-failure"
    rsf = "rspec spec --only-failures"
    rso = "rspec spec --dry-run --format doc > tmp/rspec-overview.txt && e tmp/rspec-overview.txt"

#### [Ruby on Rails](http://rubyonrails.org)

    railsb = "rails console --sandbox"
    railse = "EDITOR = 'sublime --wait' rails credentials:edit"
    railsdbm = "ber db:migrate && ber db:rollback && ber db:migrate && RAILS_ENV=test ber db:migrate"

#### [Crystal](https://crystal-lang.org)

    cr = "crystal"
    crb = "crystal build"
    crr = "crystal run"
    crd = "crystal docs"
    crdo = "open docs/index.html"
    crs = "crystal spec"

#### [Elm](http://elm-lang.org)

    elmc = "elm repl"
    elmg = "elm init"
    elmi = "elm install"
    elms = "elm reactor"
    elmt = "elm-test"
    elmp = "elm publish"

#### [Rubocop](https://github.com/bbatsov/rubocop)

    cop = "rubocop --parallel --display-cop-names --display-style-guide"
    copc = "rubocop --auto-gen-config"
    copo = "rubocop --display-cop-names --only"
    copf = "rubocop --auto-correct"
    cops = "rubocop --show-cops"
    copd = 'find . -name ".rubocop-http*" -type f -delete'

#### [SimpleCov](https://github.com/colszowka/simplecov)

    cov = "open coverage/index.html"

#### [Silver Surfer](https://github.com/ggreer/the_silver_searcher)

    agf = "ag --hidden --files-with-matches --file-search-regex"

#### [direnv](http://direnv.net)

    denva = "direnv allow"
    denvr = "direnv reload"
    denvs = "direnv status"

#### [Yarn](https://yarnpkg.com)

    yarni = "yarn install"
    yarna = "yarn add"
    yarnu = "yarn upgrade"
    yarnr = "yarn remove"

#### [Z](https://github.com/rupa/z)

    ze = "$EDITOR $HOME/.z"

#### [Path Finder](http://www.cocoatech.com/pathfinder)

    pfo = 'open -a "Path Finder.app" "$PWD"'

#### [Sublime Text](http://www.sublimetext.com)

    e = "sublime"

#### [Marked 2](http://marked2app.com)

    mo = "open -a Marked\ 2"

#### [ASCII Doctor](https://asciidoctor.org)

    ad = "asciidoctor"

#### [asciinema](https://asciinema.org)

    cin = "asciinema"
    cina = "asciinema rec --append"
    cinc = "asciinema cat"
    cinp = "asciinema play"
    cinu = "asciinema upload"
    cine = "asciinema_plus -e"

#### [duti](http://duti.org)

    dutia = "duti ~/.config/duti/configuration.duti"

#### [Terraform](https://www.terraform.io)

    tf = "terraform"
    tfa = "noti --title 'Terraform Apply' terraform apply"
    tfc = "terraform console"
    tff = "terraform fmt"
    tfg = "terraform graph | dot -Tsvg > tmp/graph.svg && open -a 'Firefox.app' tmp/graph.svg"
    tfi = "terraform init"
    tfp = "noti --title 'Terraform Plan' terraform plan"
    tfv = "terraform validate"

#### [Watch](https://gitlab.com/procps-ng/procps)

    wp = "watch --interval 1 --color --beep --exec"

### Functions

#### General

    t2s = Tab to Space - Convert file from tab to space indendation.
    cype = Colorized Type - Identical to "type" system command but with Bat support.
    eup = Environment Update - Update environment with latest software.
    iso = ISO - Builds an ISO image from mounted volume.
    pss = Process Status (specialized) - Display process status (excluding current process) and ignoring case.
    kilp = Kill Process - Kill errant processes.

#### [less](http://en.wikipedia.org/wiki/Less_(Unix))

    lessi = Less Interactive - Inspect file, interactively.

#### [License Finder](https://github.com/pivotal/LicenseFinder)

    licensei = License Finder (include) - Include license in global list.
    licensea = License Finder (add) - Adds library to global list.

#### [OpenSSL](https://openssl.org)

    sslc = SSL Certificate Creation - Create SSL certificate.

#### [curl](http://curl.haxx.se)

    curli = Curl Inspect - Inspect remote file with default editor.
    curld = Curl Diagnostics - Curl with diagnostic information for request.

#### [lsof](http://people.freebsd.org/~abe/)

    port = Port - List file activity on given port.

#### [Git](http://git-scm.com)

    gia = Git Init (all) - Initialize/re-initialize repositories in current directory.
    gafe = Git Safe - Marks repository as safe for auto-loading project's `bin/*` on path.
    groot = Git Root - Change to repository root directory regardless of current depth.
    ginfo = Git Info - Print repository overview information.
    gstats = Git Statistics - Answer statistics for current project.
    gstatsa = Git Statistics (all) - Answer statistics for all projects in current directory.
    ghurn = Git Churn - Answer commit churn for project files (sorted highest to lowest).
    gount = Git Commit Count - Answer total number of commits for current project.
    gli = Git Log (interactive) - List feature branch commits with support to show/diff individual commits.
    gld = Git Log Details - Dynamically list commit details for current feature branch or entire master branch.
    ghow = Git Show - Show commit details with optional diff support.
    gile = Git File - Show file details for a specific commit (with optional diff support).
    gistory = Git File History - View file commit history (with optional diff support).
    glameh = Git Blame History - View file commit history for a specific file and/or lines (with optional diff support).
    guthorsa = Git Authors (all) - Answer author commit activity per project (ranked highest to lowest).
    guthorc = Git Author Contributions - Answers total lines added/removed by author for repo (with emphasis on deletion).
    gsta = Git Status (all) - Answer status of projects with uncommited/unpushed changes.
    gup = Git Update - Fetch commits, prune untracked references, review each commit (optional, with diff), and pull (optional).
    gync = Git Sync - Syncs up remote changes and deletes pruned/merged branches.
    gseta = Git Set Config Value (all) - Set key value for projects in current directory.
    ggeta = Git Get Config Value (all) - Answer key value for projects in current directory.
    gunseta = Git Unset (all) - Unset key value for projects in current directory.
    gailsa = Git Email Set (all) - Sets user email for projects in current directory.
    gail = Git Email Get - Answer user email for current project.
    gaila = Git Email Get (all) - Answer user email for projects in current directory.
    gince = Git Since - Answer summarized list of activity since date/time for projects in current directory.
    gday = Git Day - Answer summarized list of current day activity for projects in current directory.
    gweek = Git Week - Answer summarized list of current week activity for projects in current directory.
    gmonth = Git Month - Answer summarized list of current month activity for projects in current directory.
    gsup = Git Standup - Answer summarized list of activity since yesterday for projects in current directory.
    gtail = Git Tail - Answer commit history since last tag for current project (copies results to clipboard).
    gtaila = Git Tail (all) - Answer commit history count since last tag for projects in current directory.
    gash = Git Stash - Creates stash.
    gashl = Git Stash List - List stashes.
    gashs = Git Stash Show - Show stash or prompt for stash to show.
    gashp = Git Stash Pop - Pop stash or prompt for stash to pop.
    gashd = Git Stash Drop - Drop stash or prompt for stash to drop.
    gasha = Git Stash (all) - Answer stash count for projects in current directory.
    gucca = Git Upstream Commit Count (all) - Answer upstream commit count since last pull for projects in current directory.
    gpua = Git Pull (all) - Pull new changes from remote branch for projects in current directory.
    galla = Git Add (all) - Apply file changes (including new files) for projects in current directory.
    gcb = Git Commit Breakpoint - Create a breakpoint (empty) commit to denote related commits in a feature branch.
    gcfi = Git Commit Fix (interactive) - Select which commit to fix within current feature branch.
    gcff = Git Commit Fix (file) - Create commit fix for file (ignores previous fixups).
    gcfp = Git Commit Fix and Push - Create fixup commit, push, and copy URL to clipboard.
    gcaa = Git Commit (all) - Commit changes (unstaged and staged) for projects in current directory.
    gcap = Git Commit and Push (all) - Commit and push changes for projects in current directory.
    gpob = Git Push Origin Branch - Pushes current branch to origin and sets upstream tracking.
    gpa = Git Push (all) - Push changes for projects in current directory.
    grbi = Git Rebase (interactive) - Rebase commits, interactively.
    grbq = Git Rebase (quick) - Rebase commits, quickly. Identical to `grbi` function but skips editor.
    gbl = Git Branch List - List local and remote branch details.
    gblo = Git Branch List Owner - List branches owned by current author or supplied author.
    gbla = Git Branch List (all) - List current branch for projects in current directory.
    gbc = Git Branch Create - Create and switch to branch.
    gbca = Git Branch Create (all) - Create and switch to branch for projects in current directory.
    gbs = Git Branch Switch - Switch between branches.
    gbsa = Git Branch Switch (all) - Switch to given branch for projects in current directory.
    gbna = Git Branch Number (all) - Answer number of branches for projects in current directory.
    gbd = Git Branch Delete - Delete branch (select local and/or remote).
    gbdl = Git Branch Delete (local) - Delete local branch.
    gbdr = Git Branch Delete (remote) - Delete remote branch.
    gbdm = Git Branch Delete (merged) - Delete remote and local merged branches.
    gbr = Git Branch Rename - Rename current branch.
    gtagr = Git Tag Rebuild - Rebuild a previous tag. WARNING: Use with caution, especially if previously published.
    gtagd = Git Tag Delete - Delete local and remote tag (if found).
    gwa = Git Worktree Add - Add and switch to new worktree.
    gwd = Git Worktree Delete - Deletes current Git worktree.
    gra = Git Remote Add - Add and track a remote repository.
    gess = Git Reset Soft - Resets previous commit (default), resets back to number of commits, or resets to specific commit.
    gesh = Git Reset Hard - Reset to HEAD, destroying all untracked, staged, and unstaged changes. UNRECOVERABLE!
    gesha = Git Reset Hard (all) - Destroy all untracked, staged, and unstaged changes for all projects in current directory. UNRECOVERABLE!
    guke = Git Nuke - Permanently destroy and erase a file from history. UNRECOVERABLE!
    gleana = Git Clean (all) - Clean uncommitted files from all projects in current directory.
    glear = Git Clear - Clear repository for packaging/shipping purposes.
    gvac = Git Verify and Clean - Verify and clean objects for current project.
    gvaca = Git Verify and Clean (all) - Verify and clean objects for projects in current directory.

#### [GitHub](https://github.com)

    gh = GitHub - View GitHub details for current project.
    ghpra = GitHub Pull Request (all) - Open pull requests for all projects in current directory (non-master branches only).

#### [PostgreSQL](http://www.postgresql.org)

    pguc = PostgreSQL User Create - Create PostgreSQL user.
    pgud = PostgreSQL User Drop - Drop PostgreSQL user.
    pgt = PostgreSQL Template - Edit PostgreSQL template.

#### [Ruby](https://www.ruby-lang.org)

    rbva = Ruby Version (all) - Show current Ruby version for all projects in current directory.
    rbua = Ruby Upgrade (all) - Upgrade Ruby projects in current directory with new Ruby version.
    rbs = Ruby Server - Serve web content from current directory via WEBrick.

#### [Ruby Gems](https://rubygems.org)

    gemdep = Gem Dependency Search - Finds a gem defined within a Gemfile or a gemspec.

#### [Bundler](http://bundler.io)

    bj = Bundler Jobs - Answer maximum Bundler job limit for current machine or automatically set it.
    bcg = Bundler Config Gem - Configure Bundler to use local gem for development purposes.
    bcim = Bundler Config Ignore Post-Install Message - Configure Bundler to ignore install messages for specified gem.
    boa = Bundle Outdated (all) - Answer outdated gems for projects in current directory.
    bua = Bundle Update (all) - Update gems for projects in current directory.
    bca = Bundle Clean (all) - Clean projects of gem artifacts (i.e. pkg folder).

#### [Rake](https://github.com/ruby/rake)

    rake = Rake - Run Rake via binstub or Bundler.
    rakea = Rake (all) - Run default Rake tasks via binstub or Bundler for projects in current directory.

#### [Code Quality](https://github.com/bkuhlmann/code_quality)

    cqa = Code Quality (all) - Run code quality tasks via binstub or Bundler for projects in current directory.
    cqi = Code Quality Issues - List all source files affected by code quality issues.

#### [RSpec](http://rspec.info)

    rspec = RSpec - Run RSpec via binstub or Bundler.
    rsb = RSpec Bisect - Debug RSpec failure using bisect to automatically determine where failure is occuring.
    rsd = RSpec Debug - Debug intermittent RSpec failure(s) by running spec(s) until failure is detected.
    rsp = RSpec Profile - Runs RSpec specs with profiling enabled.
    rsall = RSpec (all) - Run RSpec via binstub or Bundler for projects in current directory.

#### [Guard](https://github.com/guard/guard)

    guard = Guard - Run Guard via binstub or Bundler.

#### [Ruby on Rails](http://rubyonrails.org)

    railsn = Ruby on Rails New - Create new Rails application from selected template.

#### [RailRoady](https://github.com/preston/railroady)

    rr = RailRoady Models - Generate diagrams for Rails models, controllers, or states.

#### [Elm](http://elm-lang.org)

    elmm = Elm Make - Compile Elm source.
    elml = Elm Live - Watch for source code changes and recompile immediately.

#### [asciinema](https://asciinema.org)

    cinr = asciinema Record - Create new asciinema recording.

#### [Minisign](https://jedisct1.github.io/minisign)

    sigg = Minisign Generate - Generate private and public key pair.
    sigf = Minisign Sign File - Sign a file.
    sigv = Minisign Verify File - Verify signed file.

#### [Overmind](https://github.com/DarthSim/overmind)

    oms = Overmind Start - Start processes.
    omc = Overmind Connect - Connect to running process.
    omr = Overmind Restart - Restart running process.

#### [Wormhole](https://magic-wormhole.readthedocs.io)

    whs = Wormhole Send - Send encrypted path (i.e. file or directory).
    whst = Wormhole Send Text - Send encrypted text.
    whr = Wormhole Receive - Receive encrypted payload (i.e. text, file, etc.)

#### Dotfiles

    dots = Dotfiles - Learn about dotfile aliases, functions, etc.

### Git Hooks

    brakeman_check = Brakeman Check - Scan Rails project for security vulnerabilities.
    bundler_gemfile_path = Bundler Gemfile Path - Detect gem path statements.
    bundler_audit_check = Bundler Audit Check - Scans gem dependencies for security vulnerabilities.
    capybara_save_and_open_page = Capybara Save And Open Page - Detect save_and_open_page statements.
    comment_totals = Comment Totals - Print project comment totals.
    ctags_rebuild = CTags Rebuild - Rebuild project .tags file.
    elm_debug = Elm Debug - Detect debug statements.
    git_cop = Git Cop - Enforce consistent Git commits.
    git_trailer_cleaner = Git Trailer Cleaner - Remove unused/empty Git commit body trailers.
    java_script_debugger = JavaScript Debugger - Detect JavaScript debug statements.
    java_script_console = JavaScript Console - Detect JavaScript console statements.
    java_script_alert = JavaScript Alert - Detect JavaScript alert statements.
    license_finder_check = License Finder Check - Scan project for valid licenses.
    pry_binding = Pry Binding - Detect Pry debug statements.
    reek_check = Reek Check - Scan Ruby code for poor style choices.
    rspec_dotfile = RSpec Dotfile - Detect RSpec dotfile.
    rspec_focus = RSpec Focus - Detect RSpec focus.
    rspec_order = RSpec Order - Detect RSpec ordered specs.
    rubocop_check = Rubocop Check - Scan Ruby code for poor style choices.
    irb_binding = IRB Binding - Detect IRB debug statements.

### IRB, Pry, and Rails consoles

    CK.locate - Locates source code for given object and method.
    CK.search - Searches for object method for given pattern.
    CK.copy - Copies data to OS X clipboard.
    CK.paste - Pastes data from OS X clipboard.

### Pry Aliases

    'w' = "whereami"
    'c' = "continue"
    's' = "step"
    'n' = "next"
    'f' = "finish"
    "ss" = "show-source"
    "bp" = "break"
    "bpe" = "break --enable"
    "bpd" = "break --disable"
    "bpD" = "break --delete"
    "bpc" = "break --disable-all"
    "bpC" = "break --delete-all"
    "bph" = "break --help"

## Versioning

Read [Semantic Versioning](https://semver.org) for details. Briefly, it means:

- Major (X.y.z) - Incremented for any backwards incompatible public API changes.
- Minor (x.Y.z) - Incremented for new, backwards compatible, public API enhancements/fixes.
- Patch (x.y.Z) - Incremented for small, backwards compatible, bug fixes.

## Code of Conduct

Please note that this project is released with a [CODE OF CONDUCT](CODE_OF_CONDUCT.md). By
participating in this project you agree to abide by its terms.

## Contributions

Read [CONTRIBUTING](CONTRIBUTING.md) for details.

## License

Copyright 2010 [Alchemists](https://www.alchemists.io).
Read [LICENSE](LICENSE.md) for details.

## History

Read [CHANGES](CHANGES.md) for details.
Built with [Bashsmith](https://github.com/bkuhlmann/bashsmith).

## Credits

Developed by [Brooke Kuhlmann](https://www.alchemists.io) at
[Alchemists](https://www.alchemists.io).
