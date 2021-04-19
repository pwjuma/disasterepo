## Create Files
The script `createmultifiles.sh` creates multiple according to the count passed on the commandline and appends a sequential number on the filename based on the count.

It creates 5 files by default, if no count is passed on the command line with stub name "File000<seq number>.txt".

```
./createmultifiles.sh
File0001.txt created
File0002.txt created
File0003.txt created
File0004.txt created
File0005.txt created
```

You may also define your own filename with first argument as the count and second argument as the filename. 

Example:

```
./createmultifiles.sh 5 noname
noname1.txt created
noname2.txt created
noname3.txt created
noname4.txt created
noname5.txt created
```

Existing Files will be skipped

```
./createmultifiles.sh 6
File0001.txt exists, moving on
File0002.txt exists, moving on
File0003.txt exists, moving on
File0004.txt exists, moving on
File0005.txt exists, moving on
File0006.txt created

/createmultifiles.sh 6 noname
noname1.txt exists, moving on
noname2.txt exists, moving on
noname3.txt exists, moving on
noname4.txt exists, moving on
noname5.txt exists, moving on
noname6.txt created

```

## Edit Existing Files
The shell script `editfiles.sh` adds a new line to every file passed to it on the command line.
The script can edit single or multiple files.

### Edit Single file
`./editfiles.sh filename`

Example:

`./editfiles.sh File0001.txt`

### Edit Multiple Files
Use wildcards to match multiple files (similar to what you would use with `ls`)

Example:

```
./editfiles.sh File000{1..10}.txt
./editfiles.sh `ls File000{1..20}.txt` 
./editfiles.sh *.txt*
```

## Line Count
The script allows you to create a file with a defined line count, 10 lines by default.

Usage:

```
./linesinfile.sh
Created file-with-10-lines.txt with 10 lines
```

```
./linesinfile.sh 1000
Created file-with-1000-lines.rb with 1000 lines
```

```
./linesinfile.sh 1000 manylines.txt
Created manylines.txt with 1000 lines
```


## Big File

`./bigassfile.sh` 

Creates a 10MB text file


## Working with Images

`./getimages.sh`

The script uses `wget` to download images from [picsum photos](https://picsum.photos). 3 images with names "bin.jpg dump.jpg trash.jpg" are downloaded by default.

You can pass your own images names either as an array to download multiple images with the given names in the array or as a single name for a single image download.

```
./getimages.sh "cat mouse moose nairobi"

----------
--2020-07-19 14:30:33--  https://picsum.photos/500
Resolving picsum.photos (picsum.photos)... 104.26.4.30, 104.26.5.30, 172.67.74.163, ...
Connecting to picsum.photos (picsum.photos)|104.26.4.30|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://i.picsum.photos/id/628/500/500.jpg?hmac=5C1aJwdODV-2Zb9vs0fKTTbmBh-UGtOFNPT6AuNQkBI [following]
--2020-07-19 14:30:34--  https://i.picsum.photos/id/628/500/500.jpg?hmac=5C1aJwdODV-2Zb9vs0fKTTbmBh-UGtOFNPT6AuNQkBI
Resolving i.picsum.photos (i.picsum.photos)... 104.26.5.30, 172.67.74.163, 104.26.4.30, ...
Connecting to i.picsum.photos (i.picsum.photos)|104.26.5.30|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 41858 (41K) [image/jpeg]
Saving to: ‘moose.jpg’

moose.jpg                                   100%[===========================================================================================>]  40.88K  --.-KB/s    in 0.1s

2020-07-19 14:30:35 (361 KB/s) - ‘moose.jpg’ saved [41858/41858]
--2020-07-19 14:30:35--  https://picsum.photos/500
Resolving picsum.photos (picsum.photos)... 104.26.4.30, 104.26.5.30, 172.67.74.163, ...
Connecting to picsum.photos (picsum.photos)|104.26.4.30|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://i.picsum.photos/id/371/500/500.jpg?hmac=k2gvOWENObGI_VXj9CV7Vfv_-X8KgPbqOlhKIFug6Kg [following]
--2020-07-19 14:30:35--  https://i.picsum.photos/id/371/500/500.jpg?hmac=k2gvOWENObGI_VXj9CV7Vfv_-X8KgPbqOlhKIFug6Kg
Resolving i.picsum.photos (i.picsum.photos)... 104.26.5.30, 172.67.74.163, 104.26.4.30, ...
Connecting to i.picsum.photos (i.picsum.photos)|104.26.5.30|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43715 (43K) [image/jpeg]
nairobi.jpg                                 100%[===========================================================================================>]  42.69K   260KB/s    in 0.2s

2020-07-19 14:30:36 (260 KB/s) - ‘nairobi.jpg’ saved [43715/43715]

```

The images will then be embedded in your README.md.

## Generate Commits

Script:

```
commits.sh

```

Usage:

The script takes the count of commits to be generated and the filename to be edited and commited.
It uses `editfiles.sh` to edit the file(s) and `commitmsg.py` to generate the commit message from [WhatTheCommit](http://whatthecommit.com/).

By default, it will edit all the file starting with the name "File000*" and commit once.

To edit and commit a specific file 10 times:

```
commits.sh 10 myspecificfile.txt
```

You may also use wildcards:

```
commits.sh 10 *noname*.txt
```


## Commit and Push

Script

```
push.sh
```
The script commits and pushes your **all** files in the working area to the "master" branch by default. It can also take one optional argument which is the preferred remote branch you are pushing to.

```
./push.sh 
```

The Lord #1


### Editing file on 2021-04-19_21-57-15

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote




### Editing file on 2021-04-19_21-57-17

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote




### Editing file on 2021-04-19_21-57-18

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote


