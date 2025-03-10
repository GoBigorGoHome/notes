# fontspec font selection with XeLaTeX

选择非系统字体（例如 texlive 带的字体）时，只能通过字体文件名（by file name）。  
只需要写出字体文件名而不需要写出完整路径。字体文件名必须要有扩展名。  
fontspec 的文档讲得很清楚：
> XETEX and LuaTEX also allow fonts to be loaded by file name instead of font name. When you
have a very large collection of fonts, you will sometimes not wish to have them all installed
in your system’s font directories. In this case, it is more convenient to load them from a different
location on your disk. This technique is also necessary in XETEX when loading OpenType
fonts that are present within your TEX distribution, such as `/usr/local/texlive/2013/texmf-dist/fonts/opentype/public`.
> **Fonts in such locations are visible to XETEX but cannot be loaded by font name, only file name;** LuaTEX does not have this restriction.
> 
> When selecting fonts by file name, any font that can be found in the default search paths
may be used directly (including in the current directory) without having to explicitly define
the location of the font file on disk.
> 
> Fonts selected by filename must include bold and italic variants explicitly, unless a
.fontspec file is supplied for the font family (see Section 2.3). We’ll give some first examples
specifying everything explicitly:
> ```
> \setmainfont{texgyrepagella-regular.otf}[
> BoldFont = texgyrepagella-bold.otf ,
> ItalicFont = texgyrepagella-italic.otf ,
> BoldItalicFont = texgyrepagella-bolditalic.otf ]
> ```
> fontspec knows that the font is to be selected by file name by the presence of the ‘.otf’ extension.


# \varnothing

`\usepackage{amssymb}`

# 定义 \floor 和 \ceil

https://tex.stackexchange.com/questions/42271/floor-and-ceiling-functions

`\DeclarePairedDelimiter{\ceil}{\lceil}{\rceil}`

if called as `\ceil*{x}` it will add `\left` and `\right`.

# 用 pgfplots 画函数图像

例一：
```latex
\begin{tikzpicture}
\begin{axis}[
axis lines=center, %有坐标轴，坐标轴在中心。
xlabel=$x$,
ylabel=$f(x)$,
title ={$f(x) = x^2$}
]
\addplot [
color=red,
domain=-10:10,
samples=201,
]
{x^2};
\end{axis}
\end{tikzpicture}
```
例二：
```latex
\begin{tikzpicture}
\begin{axis}[
axis lines=none, %无坐标轴。
title ={$f(x) = x^2$}
]
\addplot [
color=red,
domain=-10:10,
samples=201,
]
{x^2};
\end{axis}
\end{tikzpicture}
```




[Plot a function of logarithm with PGFplots](https://tex.stackexchange.com/q/444375/135216)  
有函数 `log(x)` 和 `log2(x)` 可用，其他底数的对数需要用换底公式。

[How to plot x^(1/3)?](https://tex.stackexchange.com/q/144454/135216)  
`x/abs(x)*abs(x)^(1/3)`

# What's the difference between \mathrm and \operatorname?

https://tex.stackexchange.com/q/19180/135216

# 排版伪代码

```latex
\documentclass{ctexart}
\usepackage[vlined]{algorithm2e} %vlined选项用来消除block结尾的end
\SetKwProg{Fn}{}{:}{}
\DontPrintSemicolon %不要在语句末尾打印分号

\begin{document}
\begin{algorithm}[H]
    \Fn{binary\_search($N$)}{
        $w \gets 1$ \tcp{注释1} %行内注释。行末不需要也不能加\\
        $b \gets N$ \tcp*{注释2} %右对齐
        \While{$w + 1 < b$} {
            $m \gets \lfloor (w+b)/2 \rfloor $ \\
            \If (\tcp*[f]{注释3}) {第$m$个球是白色} {
                $w \gets m$
            } \Else {
                $b \gets m$
            }
        }
        \Return{$w$}
    }
\end{algorithm}
\end{document}
```
