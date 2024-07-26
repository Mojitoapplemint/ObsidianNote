- `t`: Text mode. Only run this snippet outside math
- `m`: Math mode. Only run this snippet inside math. Shorthand for both `M` and `n`
- `M`: Block math mode. Only run this snippet inside a `$$ ... $$` block
- `n`: Inline math mode. Only run this snippet inside a `$ ... $` block
- `A`: Auto. Expand this snippet as soon as the trigger is typed. If omitted, the Tab key must be pressed to expand the snippet
- `r`: [Regex](https://github.com/artisticat1/obsidian-latex-suite/blob/main/DOCS.md#regex-snippets). The `trigger` will be treated as a regular expression
- `v`:[Visual](https://github.com/artisticat1/obsidian-latex-suite/blob/main/DOCS.md#visual-snippets). Only run this snippet on a selection. The trigger should be a single character
- `w`: Word boundary. Only run this snippet when the trigger is preceded (and followed by) a word delimiter, such as `.`, `,`, or `-`.
- `c`: Code mode. Only run this snippet inside a ` ``` ... ``` ` block

```json
//new
    {trigger: "/", replacement: "\\frac{$0}{$1}", options: "mA"},
    {trigger: "any", replacement: "\\forall \text{ }", options: "mA"},
    {trigger: "ext", replacement: "\\exists \text{ }", options: "MA"},
    {trigger: "[[a-zA-Z]][[0-9i]]", replacement: "[[0]]_{[[1]]}", options: "rmA"},
    {trigger: "f", replacement: "f($0)", options: "mA"},
    {trigger: "g", replacement: "g($0)", options: "mA"},
    {trigger: "pi", replacement: "\\pi", options: "mA"},
    {trigger: "^", replacement: "^{$0}", options: "mA"},
    {trigger: "\\C", replacement: "\\mathbb{C}", options: "tA"},
    {trigger: "\\R", replacement: "\\mathbb{R}", options: "tA"},
    {trigger: "\\Z", replacement: "\\mathbb{Z}", options: "tA"},
    {trigger: "Pd", replacement: "\\partial ", options: "mA"},
    {trigger: "thus", replacement: "\\therefore ", options: "mA"},
    {trigger: "aprx", replacement: "\\approx ", options: "mA"},
     {trigger: "int", replacement: "\\int^{$0}_{$1}$2 d{$3} $4", options: "mA"},
    {trigger: "Int", replacement: "\\int $0 d{$1} $2", options: "mA"},
    {trigger: "sum", replacement: "\\sum^{$0}_{$1}$2 ", options: "mA"},
    {trigger: "Sum", replacement: "\\sum", options: "mA"},
    {trigger: "rra", replacement: "\\rightrightarrows", options: "mA"},

//Override
	{trigger: "lim", replacement: "\\lim_{$0\\to $1}{$2}$3", options: "mA"},
	{trigger: "inf", replacement: "\\infty", options: "mA"},
	{trigger: "int", replacement: "\\int $0 \\, d${1:x}{$2}$3", options: "mA"},
	{trigger: "txt", replacement: "\\text{$0}", options: "mA"},

//Delete
{trigger: "([^\\\\])(${GREEK}|${SYMBOL})", replacement: "[[0]]\\[[1]]", options: "rmA", description: "Add backslash before greek letters and symbols"},
{trigger: "\\\\(${GREEK}|${SYMBOL}|${SHORT_SYMBOL})([A-Za-z])", replacement: "\\[[0]] [[1]]", options: "rmA"},
{trigger: "set", replacement: "\\{ $0 \\}$1", options: "mA"},
```


$a_{i}$