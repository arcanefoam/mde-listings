# mde_listings
A LaTeX Listings language definition file for languages used by the MDE community

## Supported Languages

- OCL (Eclipse)
- OCLinEcore
- QVTr
- QVTc
- EOL (Epsilon)
- ETL (Epsilon)
- ATL

## Keyword Groups (for appearance)
The Listings package supports one or more keyword lists for each langauge. This allows to use different formatting options for each group. Languages defined in this file follow a two list approach. The lanuage syntax keywords (e.g. in, let, for, rule, etc.) are in list one. List two contains other langauge specific identifiers that are not part of the syntax, for example available operations on collections (OCL, EOL) or primitive type names (String, Sequence, etc.).

In your tex file you can then define a different style for each list of keywords:
```
\lstset{
    ...
    keywordstyle=\bfseries,						            % list 1
    keywordstyle=[2]\bfseries\textsl,			        % list 2
    ...
}
```

## installation (basic)
Either clone or download the files in the repository.
Copy files `lstlandmde.sty` and `lstlocal.cfg` to your LaTeX Listings package installation folder. If you use a package manager,
the folder should be in your tex installation folder:
```
<tex-instalation>\tex\latex\listings
```
E.g. in my computer (windows) it is `C:\MiKTeX 2.9\tex\latex\listings`.

If you use a local tex folder then you should know where it is ;)

## installation (advanced)
If you have other style files you have already added to your listings installation then you need
to merge your lstlocal.cfg file with the one from this repository.

As a minimum make usre that lstlangmde.sty is added to your the list of \lstlanguagefiles.
Optionally, also copy the default dialect definitions.

## Refreshing latex database
After instalation you need to refresh your database.

###For Windows (assuming your TeX distribution is MiKTeX):

1. Start the Settings windows of MiKTeX with the command sequence: Windows Start -- all programms -- Maintenance (Admin) -- Settings (Admin)
2. Choose General and click on Refresh FNDB

Note that if you used the "only this user" installation you can only use the non-admin commands.

###For Linux / Mac
Running `sudo texhash` should do the trick.

## Contributing more languages
If you have created language definitions for other languages please create a fork, add them and do a pull request.

## TODO
Probably we would like a small tex file that showcases all the languages so users can see the outcome and also work for testing definitions (new or changes).
