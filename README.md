# mde_listings
A LaTeX Listings language definition file for languages used by the MDE community

## installation
Either clone or download the files in the repository.
Copy both files to your LaTeX Listings package installation folder. If you use a package manager
the folder should be in your tex installation folder:
```
<tex-instalation>\tex\latex\listings
```
E.g. in my computer (windows) it is `C:\MiKTeX 2.9\tex\latex\listings`.
If you use a local tex folder then you should know where it is ;)

After that, you need to refresh your database.

###For Windows (assuming your TeX distribution is MiKTeX):

1. Start the Settings windows of MiKTeX with the command sequence: Windows Start -- all programms -- Maintenance (Admin) -- Settings (Admin)
2. Choose General and click on Refresh FNDB

Note that if you used the "only this user" installation you can only use the non-admin commands.

###For Linux / Mac
Running `sudo texhash` should do the trick.
