WIPWIPWIPWIPWIPWIPWIPWIPWIPWIPWIP

# README.md

Configs, dot files, installation instructions etc. Mostly for Python-based data science work on Mac. Also a reference for setting up a new machine.


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

Using `nbconvert` templates per https://github.com/ipython/ipython/wiki/Cookbook:%20nbconvert%20templates

Use template supplied in this repo `templates/classic_mod.tplx`. Depending on where called from, likely need to change filepath.

Use as:

```zsh
$> jupyter nbconvert --to pdf --template templates/classic_mod.tplx <NOTEBOOK>.ipynb
```

I based this on `classic.tplx` from https://github.com/t-makaro/nb_pdf_template (also see https://pypi.org/project/nb-pdf-template/). Would like to use just that but:

1. I want my mods to fontsize etc which I think are better, and
2. This package hasn't kept up with changes to `nbconvert` and some filepaths are wrong:

    Note as-at 2021-02-24 on v3.0.0 I needed to add a new dir `latex` under nbconvert's package path

    `/Users/jon/opt/anaconda3/envs/<ENV>/lib/python3.8/site-packages/nbconvert/templates/`

    So that this line worked:

    ```{install.py}python
    dst = os.path.abspath(os.path.join(nbconvert_path, "templates", "latex"))
    ```
