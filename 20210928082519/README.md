# Disable `clang-format` for sections

Special comments can be added around sections are hand-formatted and you do not
want to be reformatted be `clang-format`.

Like this:

```cpp
// clang-format off
std::vector<int> testcases[][2] = {
  {
    {1, 3} , {2}
  },
  {
    {1, 2}, {3, 4}
  },
  {
    {0, 0}, {0, 0}
  },
  {
    {}, {1}
  },
  {
    {2}, {}
  }
};
// clang-format on
```

Note that the single space after the `//` is important.
