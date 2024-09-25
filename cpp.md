# operator>> can't read decayed C-style strings since C++20
> In C++20, `operator>>` was changed so that it only works for inputting non-decayed C-style strings. This allows `operator>>` to extract only as many characters as the C-style string’s length will allow, preventing overflow. But this also means you can no longer use operator>> to input to decayed C-style strings.

```cpp
char s[1005];
cin >> s; // OK
cin >> s + 1; // error since C++20
```
