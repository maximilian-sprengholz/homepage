# Efficiency

_The following help files should allow you to work more efficiently on your projects._

## Atom & Hydrogen

This file helps you using the [Atom](https://www.atom.io) text editor with the [Hydrogen](https://nteract.gitbooks.io/hydrogen/content/) package to run Stata and R code from within Atom via `stata_kernel` and `IRkernel`

### Dependencies
<u>Python</u>
Install a Python 3.5+ distribution. I recommend the [miniconda distribution](https://docs.conda.io/en/latest/miniconda.html), but you can also use the full anaconda or any other distribution. Please note that depending on the distribution, commands might differ.

### Stata
<u>Stata_kernel</u>

Install `stata_kernel` by Kyle Barron via shell:
```bash
# make sure installing in the desired environment
# via conda
conda install -c conda-forge stata_kernel
# via pip
pip install stata_kernel

# install kernel-spec
# globally
python -m stata_kernel.install
# in environment different from base
python -m stata_kernel install --user --name my-project-and-kernel-name
```
See the full [documentation](https://kylebarron.dev/stata_kernel/) for further information and additional options (e.g. on Python versioning, JupyterLab, ...).

<u>Stata automation library (Windows only)</u>
- create shortcut to Stata.exe (on Desktop is ok)
- open shortcut properties, add `/Register` to target link
  So if your target link is...
  ```bash
  "C:\Program Files (x86)\Stata15\StataSE-64.exe"
  ```
  ...it should look like this:
  ```bash
  "C:\Program Files (x86)\Stata15\StataSE-64.exe" /Register
  ```
- run as admin (unfortunately necessary, see [here](https://www.stata.com/automation/))

### R
<u>IRkernel</u>

Within Anaconda Powershell Prompt, change into the directory where your R.exe is and run R from within Anaconda. For example:
```bash
cd "c:/Program Files/R/R-3.6.0/bin"
./R.exe
```
Download (choose a close download mirror after the first command) and install IRkernel by running:
```bash
install.packages('IRkernel')
IRkernel::installspec()
```

### Atom
Press `ctrl/cmd`+`,`, select __Install__, search for and add the following packages:
- language-stata
- atom-language-r (maintained and enhanced version of language-r)
- hydrogen

Depending on the kernels installed, open a `.do` or `.r` file for testing purposes. Press `ctrl/cmd`+`shift`+`l` and select __Stata__ or __R__ as language. You should see a notification from Hydrogen that the respective kernels have been updated. Start hydrogen execution by pressing `ctrl/cmd`+`alt`+`enter`. You should see the output directly in Atom.

<u>Troubleshooting:</u>

If you get an error message upon execution that no kernels are installed at all, try:
- restarting Atom
- Check if your Python installation was successful by running `python` in the (Anaconda) command prompt. You should see that you have at least Python 3.5 installed on your system. If not, update, for example by running `conda update python`. Install kernels again (existing installations will be overwritten).

If you get the error message that no kernel for language __Stata__ or __R__ is installed, try:
- `ctrl/cmd`+`shift`+`p` and select __Hydrogen: Update kernels__
- restart Atom
