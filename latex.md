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

