sha512
======

Class to create SHA512 checksum from file or string

<b>Example</b>

```c++

#include "sha512\sha512.h"

int main(int argc,char** argv){

  char cstring[] = "Foo baz, testing.";
  std::string str = cstring;

  /* SHA512 from std::string */
  printf("sha512sum: %s\n",  sha512( str ).c_str());
  
  /* SHA512 from c-string */
  printf("sha512sum: %s\n",  sha512( cstring, strlen(cstring) ).c_str());

  /* SHA512 from filename */
  printf("sha512file: %s\n", sha512file("README.md").c_str());
  
  /* SHA512 from opened file */
  std::FILE* file = std::fopen("README.md", "rb");
  printf("sha512file: %s\n", sha512file(file).c_str());
  std::fclose(file);

  /* we're done */
  return EXIT_SUCCESS;
}

```
