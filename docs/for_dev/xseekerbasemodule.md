# Installation of XSeekerBaseModule

You will need to go to the gitlab repository: https://unh-pfem-gitlab.ara.inrae.fr/chopin/xseekerbasemodule

## Cloning the repository

To start, you will need to clone the gitlab repository: https://unh-pfem-gitlab.ara.inrae.fr/chopin/xseekerbasemodule
To be able to do this, you need an account on this platform and also an access to this repository. After that, in a terminal on your computer you have to write:
```bash
git clone https://unh-pfem-gitlab.ara.inrae.fr/chopin/xseekerbasemodule.git
```

This will copy the folder on your computer. To access to it you should do:
```bash
cd my_personal_path/xseekerbasemodule
```
where `my_personal_path` is the path to access your folder just cloned !

## Requirement

-   R-4.0.0
-   rmarkdown
-   roxygen2
-   devtools

``` bash
~/my_R_path/R -e "install.packages(
    c(
        'devtools',
        'roxygen2',
        'rmarkdown'
    ), repos='https://cloud.r-project.org'
)"
```
where you have to change with your own R path !

## Modification of config.sh file

Define where to find R in the config file (config.sh):

![config_file](\images\config_file.png)

Then, you can configure your folder running the configure file:
```bash
./configure
```


## Building and installation

Once you changed your R path in the config file, you will be able to run the configure script:

```bash
make build
make install
```

This will install the package in the default R's library. So, it becomes available to XSeeker's packages.
