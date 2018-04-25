# This repo is a collection of tricks and fixes to all kinds of weird issues in my CS life.
[ReadMe editor](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

## Opencv

### make project dependent on opencv, run this before make
**export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:~/FaceRec/ThirdParty/opencv/release/lib/**

## CUDA

### cuDNN STATUS_BAD_PARAM error thrown
preprocessor definition could be the reason

## File System

### new line encoding differences between OS
In windows (non-binary), "\n" in string is automatically encoded in "\r\n" (CR LF) which is 0X0d0a. 
However in c++ on server, std::endl is "\n" (LR) which is equal to << "\n" << std::flush, 0X0a in hexidecimal
In general, newline is "\r\n" (CR LF) in Windows, "\n" (LF) in Unix, "\r" (CR) in Macintosh 
specific solution in python, write with option 'wb' where 'b' is for binary format (LF)

### a ^M is added at the end of every line in CR LF
`sed -e "s/^M//" filename > newfilename`

## Docker

### docker permission denied only in tmux
tmux might be missing some env variable
execute **su - <username>**
may help resolve this
  
### saved files in container will be lost once container is re-built from docker image
always save any changes in shared directory

## tmux

### Kill current panel
Ctrl-A x

## conda

### activate environment
`source activate newenv`

## cmd tools

### ldd
try `ldd EXEC` will list all dependencies of the EXECTUABLE
