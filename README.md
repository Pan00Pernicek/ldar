# ldar
lenght determined file archive format

currently not supporting subdirectories but i plan to implement that in fututre by simple putting archive into archive...

usage:
  unpack
  pack

archive syntax:
  first char of archive defines how big definition of sizes should be, by default it uses "9" althought it will propably change in future, unpack part can unpack anything from 1 - 9 currently. then there will be definition of size of file name, number of digits defined with first char of archive, then there is name of file itself, and then definiton of size of file content, similiar to filename size definition, and then there is file content itself:
  
  example:
  ```
  205hello12hello world
  
  ```
  creates file hello with content hello
  world
  
