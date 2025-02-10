# 有行号的代码块

<pre>
```cpp {*}{lines: true}
int main() {
  int sum = 0;
  int v = 1;
  while (v <= 9)
  {
    sum += v * v * v;
    ++v;
  }
  std::cout << sum << '\n';
  return 0;
}
```
</pre>

注意：`{*}` 和 `{lines: true}` 之间**不能**有空格。

`{*}` 可换为 `{all}`。
