XSeeker is an application that you can launch directly on your own computer. To be able to do this you probably need some informatician skills because a lot of things are used during this installation and running.

You will also need a Linux OS because XSeeker has not been built for Windows expectations.


## XSeeker Base Module

This R package defines one signle S5 class: XSeekerBaseModule. The goal of this class is to define a unified structure for all modules (plugins) from the XSeeker project. All XSeeker's module should inherit from it (they are S5 classes), so their structure is identical which means they share some attributes and some methods, that are used by XSeeker to enrich it's functionalities.

It was packaged separatly from XSeeker to allow people to develop XSeeker's module without having to depend from XSeeker. This way, we can develop XSeeker modules and use them in other projects.

Because XSeeker uses RShiny to define the server and the UI of its application, the XSeeker modules' server and UI must be created using RShiny.

XSeekerBaseModules is designed to work with XSeeker, so its structure is directly dependant to XSeeker's design.

XSeeker loads modules to add some bricks of UI/server/tools to it's own UI/server/toolSet. The UI and server bricks must use the RShiny package's design.

This is why XSeeker's modules are separated in four main parts:

-   The UI bricks ;
-   The Server bricks ;
-   The tool set ;
-   The module that keep things packed together.

The XSeekerBaseModule only define one file: XSeekerBaseModule.R. This file defines the super-class and attributes/methods for all parts of Xseeker's modules, and does not separate the ui server and tools functions because they are - for most of them - empty functions.

In a concern of documentation centralisation, we recommand to read [XSeeker's documentation](https://services.pfem.clermont.inra.fr/gitlab/chopin/xseeker/blob/master/TECHNICAL_DOC.md#xseekers-base-module-class) on how to write XSeeker's module using this class as a super-class.

## XSeeker application

A tool to visualise and annotate data from LC-MSMS.

The prefered workflow to process your data is:

{mzxml} -\> xcms{rdata} -\> camera{rdata} -\> XSeekerPreparator{sqlite} -\> XSeeker

But it is still possible to only do:

{mzxml} -\> xcms{rdata} -\> camera{rdata} -\> XSeeker

This way, you will have to choose the files you want to visualize, but it will take some time to import them.

XSeeker can output csv, tsv and mzTab files, so annotations can be used in other programs and/or is human readable/writable.

XSeeker can also output an sqlite file, exactly like the one it takes in input. This file can be used to stop your anotation and resume the process later. It’s like an XSeeker save file.