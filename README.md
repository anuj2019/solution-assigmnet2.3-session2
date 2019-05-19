# solution-assigmnet2.3-session2
R 
1. How to Import SAS XPORT Files into R With The foreign package	read.xport: Import a SAS XPORT File

library(foreign)
> read.xport("test.xpt")
Error in file(con, "rb") : cannot open the connection
In addition: Warning message:
In file(con, "rb") : cannot open file 'test.xpt': No such file or directory
> 
> read.xport(file,
+            force.integer=TRUE,
+            formats=NULL,
+            name.chars=NULL,
+            names.tolower=FALSE,
+            keep=NULL,
+            drop=NULL,
+            as.is=0.95,
+            verbose=FALSE,
+            as.list=FALSE,
+            include.formats=FALSE
+            )
Error in as.character(x) : 
  cannot coerce type 'closure' to vector of type 'character'
> lookup.xport("test.xpt")
Error in lookup.xport.inner(file) : 
  unable to open file: 'No such file or directory'Read a SAS XPORT format file and return the contained dataset(s).
Usage
 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12	read.xport(file,
           force.integer=TRUE,
           formats=NULL,
           name.chars=NULL,
           names.tolower=FALSE,
           keep=NULL,
           drop=NULL,
           as.is=0.95,
           verbose=FALSE,
           as.list=FALSE,
           include.formats=FALSE
           )

Arguments
file	Character string specifying the name or URL of a SAS XPORT file.
force.integer	Logical flag indicating whether integer-valued variables should be returned as integers (TRUE) or doubles (FALSE). Variables outside the supported integer range (.Machine$integer.max) will always be converted to doubles.
formats	a data frame or list (like that created by foreign:::read.xport) containing PROC FORMAT output, if such output is not stored in the main transport file.
name.chars	Vector of additional characters permissible in variable names. By default, only the alpha and numeric characters ([A-Za-z0-9]) and periods ('.') are permitted. All other characters are converted into periods ('.').
names.tolower	Logical indicating whether variable and dataset names should be converted to lowercase (TRUE) or left uppercase (FALSE)
keep	a vector of names of SAS datasets to process. This list must include PROC FORMAT dataset if it is present for datasets to use use any of its value label formats.
drop	a vector of names of SAS datasets to ignore (original SAS upper case names)
as.is	Either a logical flag indicating whether SAS character variables should be preserved as character objects (TRUE) or factor objects (FALSE), or a fractional cutoff between 0 and 1.
When a fractional cutoff is provided, character variables containing a more than this fraction of unique values will be stored as a character variables. This is done in order to preserve space, since factors must store both the integer factor codes and the character factor labels.
verbose	Logical indicating whether progress should be printed during the data loading and conversion process.
as.list	Logical indicating whether to return a list even if the SAS xport file contains only only one dataset.
include.formats	Logical indicating whether to include SAS format information (if present) in the returned list
read.xport {foreign}	R Documentation
Read a SAS XPORT Format Library
Description
Reads a file as a SAS XPORT format library and returns a list of data.frames.
Usage
read.xport(file)
Arguments

