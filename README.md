WIP

# README.md

Configs, dot files, installation instructions etc. Mostly for Python-based data science work on Mac. Also a pretty good reference for setting up a new machine.


## Essential Mac Installs

### Homebrew

Essential package manager. https://brew.sh

Just follow the instructions

Some packages I like to use:

```bash
brew install wget htop zsh powerlevel10k hugo parquet-tools direnv
```




## Useful Mac Installs

### Direnv

Shell unclutterer https://direnv.net

I primarily use this to auto activate conda environments per repo

```zsh
$> brew install direnv
```

Requires `conda init` to create shell references

```zsh
$> conda init
```

Create files per repo like

```zsh
$> cat 'eval "$(conda shell.zsh hook)"; conda activate <ENV>' > .envrc
```


### Install Tex on Mac

Use BasicTex

```zsh
$> brew install --cask basictex
$> sudo tlmgr install adjustbox bbding collectbox enumitem environ framed import multirow mdframed needspace ntheorem tabu tcolorbox textpos titling titlesec threeparttable tocloft trimspaces varwidth wrapfig collection-fontsrecommended
```


### Install nicer PDF notebook rendering

Using https://pypi.org/project/nb-pdf-template/

Assume inside conda env

```zsh
$> pip install nb_pdf_template
$> python -m nb_pdf_template.install
```


