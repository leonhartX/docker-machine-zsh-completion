# docker-machine-zsh-completion
A more functional and up-to-date zsh completion for docker-machine

This has been merged in [docker-machine](https://github.com/docker/machine), but clone this repo to your completion path maybe a good way to easily keep it up-to-date.

## Installing Command Completion

### Manual installation
Place the completion scripts in your `/path/to/zsh/completion`, using e.g. `~/.zsh/completion/`

    mkdir -p ~/.zsh/completion
    git clone https://github.com/leonhartX/docker-machine-zsh-completion.git ~/.zsh/completion/docker-machine

Include the directory in your `$fpath`, e.g. by adding in `~/.zshrc`

    fpath=(~/.zsh/completion/docker-machine $fpath)

Make sure `compinit` is loaded or do it by adding in `~/.zshrc`

    autoload -Uz compinit && compinit -i

Then reload your shell

    exec $SHELL -l

### Using oh-my-zsh

If you use [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) then just clone the repository inside your oh-my-zsh repo:

	git clone https://github.com/leonhartX/docker-machine-zsh-completion.git ~/.oh-my-zsh/custom/plugins/docker-machine

and enable it in your `.zshrc`:

	plugins+=(docker-machine)
	autoload -U compinit && compinit

### Available completions
Depending on what you typed on the command line so far, it will complete

 - available docker-machine commands
 - options that are available for a particular command
 - machine names that make sense in a given context (e.g. `docker-machine ip` with only running machines vs. `docker-machine rm` with all machines).
 - swarm discovery that are available to join in.
 - driver options (e.g. `amazonec2-ami`) that are available for a particular driver after the `--driver,-d` options is specified.
 - arguments for selected options, e.g. `docker-machine ls --filter` will complete some filter options like `driver` and `name`.

