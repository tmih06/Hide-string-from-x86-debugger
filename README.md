## Hide string

This header file provides a way to hide strings from [x86 debuggers](https://github.com/x64dbg/x64dbg). It does this by encrypting the string using a stream cipher. The encrypted string is then stored in a structure that also contains the seed used to encrypt it.

To use this header file, you first need to include it in your source file. Then, you can use the `enc()` macro to encrypt a string. The `enc()` macro takes a single argument, which is the string to be encrypted. The macro will return a `std::string` object that contains the encrypted string.

```c++
#include "no_string.hpp"
```

For example, the following code encrypts the string "Hello, world!" and stores it in the variable `encrypted_string`:

```c++
#include "no_string.hpp"

int main() {
  std::string encrypted_string = enc("Hello, world!");
  return 0;
}
```

The `no_string` header file also provides a number of other functions that can be used to work with encrypted strings. These functions include:

-   `enc()` - Encrypts a string using a stream cipher.
-   `seed()` - Generates a seed that can be used to encrypt or decrypt a string.
-   `modulus()` - Returns the modulus used by the stream cipher.

The `no_string` header file can be used to hide strings from x86 debuggers. This can be useful for security purposes, as it can prevent attackers from seeing sensitive information in your code.


## Example :

#The normal hello_world.cpp: [here](https://github.com/tmih06/Hide-string-from-x86-debugger/blob/main/example/normal.cpp)
```c++
#include <iostream>
int main()
{
    std::cout << "Hello, world";
}
```
# How its look in x86 debugger:
![](https://github.com/tmih06/Hide-string-from-x86-debugger/blob/main/img/How%20does%20it%20look%20without%20encrypt.png)

# The hide string hello_world.cpp: **  [here](https://github.com/tmih06/Hide-string-from-x86-debugger/blob/main/example/encrypted.cpp)
```c++
#include "no_string.hpp"
#include <iostream>
int main()
{
    std::cout << enc("Hello, world");
}
```
# How its look in x86 debugger:
![](https://github.com/tmih06/Hide-string-from-x86-debugger/blob/main/img/hide%20string.png)

As you can see, just 1 more line and use the enc(), the string cannot be searched in x86 debugger
