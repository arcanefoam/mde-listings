# MDE Listings
A LaTeX Listings language definition file for languages used by the MDE community

## Supported Languages

- OCL (Eclipse)
- OCLinEcore
- QVTr
- QVTc
- EOL (Epsilon)
- EVL (Epsilon)
- ETL (Epsilon)
- EWL (Epsilon)
- EGL (Epsilon)
- ECL (Epsilon)
- EML (Epsilon)
- Flock (Epsilon)
- EPL (Epsilon)
- ATL
- Emfatic 

## Keyword Groups (for appearance)
The Listings package supports one or more keyword lists for each language. This allows to use different formatting
options for each group. Languages defined in this file follow a two list approach. The language syntax keywords
(e.g. in, let, for, rule, etc.) are in list one. List two contains other language specific identifiers that are not part
of the syntax, for example available operations on collections (OCL, EOL) or primitive type names (String, Sequence,
etc.).

In your tex file you can then define a different style for each list of keywords:
```
\lstset{
    ...
    keywordstyle=\bfseries,              % list 1
    keywordstyle=[2]\bfseries\textsl,    % list 2
    ...
}
```

## Installation

### Quick and Dirty
Download the files in the repository as a zip and extract them in your preferred location. 
Copy `lstlang0.sty` and `lstlangmde_def.tex` to the folder where your tex file(s) resides.
The MDE languages should now be available to use for listings.

**NOTE**: This assumes you have not previously used the `lstlang0.sty` to add new languages.
If so, you will have to merge the two files.


### Install in a TeX local/user tree
This seems to be the most convenient way:
1. No need to mess with your TeX installation
2. No "fuss" about having a git repo in the TeX installation (see #1)
3. Easy to replicate across machines (i.e. the folder structure is the same)
4. Uses the mde-listings git repo (easy keep up to date)
 
Adding a user/local tree is platform dependent. 
#### Windows Users (MikTeX)
*Speravir* (@Tex-StackExchnge) has some of the most helpful posts about MikTex. Please read [this one](https://tex.stackexchange.com/questions/69483/create-a-local-texmf-tree-in-miktex) and decide
where to create your local/user listings folder. 
Make sure you at least have the `tex\latex` structure, and underneath that a `listings` folder, e.g.
`c:\data\localtexmf\tex\latex\listings`

#### Nix users
I would recommend you to use your TeXMF user folder. The easiest way to create the listings folder is:
```
sudo mkdir -p $(kpsewhich -var-value TEXMFHOME)/tex/latex/listings
```
The `$(kpsewhich -var-value TEXMFHOME)` makes uses of the TEXMFHOME variable to create the folder (somewhere in your
User [library] folder)

Once you have created a listings folder, clone the mde-listings repository to that folder (nix users can use the 
kpsewhich trick to locate the folder)

```
git clone https://github.com/arcanefoam/mde-listings.git path/to/local/tex/latex/listings
```

After you have cloned (and after each time you pull new changes) you need to refresh your latex database.

#### Windows (MikTeX)
Use the refresh button, from the general tab in the settings application.

#### Nix
```
sudo texhash
```

### For all users (advanced)
Follow a similar procedure as before, but clone the mde-listings repo to your TeX installation. In Nix you can find this
by using `TEXMFLOCAL` instead of `TEXMFHOME`. In Windows (MikTeX) depends on your type of installation. 

**NOTE**: Cloning the repository into the local TeX installation can cause issues. For this type of installation I would
rather use the unzip-copy approach. USE AT YOUR OWN RISK! 


## Contributing more languages
If you have created language definitions for other languages please create a fork, add them and do a pull request.

## TODO
- Probably we would like a small tex file that showcases all the languages so users can see the outcome and also work for testing definitions (new or changes).
- Add default *.prf files for the supported languages (probably providing a format that resembles their native look).
