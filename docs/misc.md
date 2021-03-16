# Miscellaneous helpful stuff

## R

### Set directory for R Studio library (Windows)

Open path variable editor via command prompt:
```bash
rundll32 sysdm.cpl,EditEnvironmentVariables
```
Add new:
```bash
Variable: R_LIBS_USER
Value:    "C:\Users\myusername\Seafile\MySyncedDir\R\Library"
```

Selecting __Tools__ > __Install Packages__ in R Studio, you should see your path selected below __Install to Library__.
