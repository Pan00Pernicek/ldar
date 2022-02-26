# ldar
lenght determined file archive format

WIP, it can nuke your data when something goes wrong!!!
 (i guess i can't be never sure about that until i check every variable if its correct)

~~currently not supporting subdirectories, but i plan to implement that in future by simply putting archive into archive...~~
subdirectories are now implemented via putting archive into archive
	- as result of that, any ldar archive inside ldar archive will be unpacked regardless of it being produced by packing folder or it was here from before, i plan to fix that with support of metadata, currently workaround is changing file extension of archive you dont want to be unpacked to something else than .ldar

usage:
  unpack
  pack

archive syntax:
  first two chars of archive defines how big definition of sizes should be, by default it uses lowest possible amount for given directory, unpack part can unpack anything from 01 - 99 currently. then there will be definition of size of file name, number of digits defined with first two chars of archive, then there is name of file itself, and then definiton of size of file content, similiar to filename size definition, and then there is file content itself:
  
  example:
  ```
  0205hello12hello world
  
  ```
  creates file hello with content hello
  world
  

limits:
  in theory max size of file in ldar archive is number with 99 zeroes

  ldar can't handle metadata currently althought i may implement it one day with "name metadata content name metadata content..." instead of current "name content name content..."

  ldar can't handle symbolic links
