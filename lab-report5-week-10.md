# Lab Report 5 - Week 10 Markdown Parse Bugs
[Back](https://bimai25.github.io/cse15l-lab-reports/index.html)

## Finding Different Results
In order to find tests with different results, I used the `diff` command in the terminal to compare the ouputs of the `test-files` directory on Joe's `markdown-parse` and my group's `markdown-parse`. From the output of the `diff` command, I went to each line in the ouput test files to see what the differences were.

## Test File `201.md`
```
[foo]: <bar>(baz)

[foo]
```
**Joe's Output:** `[baz]` | **Group Output:** `[]`

My group's output is correct since `201.md` does not contain a link.

The bug in Joe's implementation is that while he checks to open and close parentheses as well as open and close brackets, it does not check to see if the open parenthesis comes immediately after the close bracket.
### `Joe's Markdown Parse`
```
int closeParen = findCloseParen(markdown, openParen);

if(nextOpenBracket == -1 || nextCloseBracket == -1
        || closeParen == -1 || openParen == -1) {
    return toReturn;
}
```
This check is key because a link is only valid if the open parenthesis comes immediately after the close bracket, which it does not in `201.md`.

## Test File `516.md`
```
[![moon](moon.jpg)](/uri)
```
**Joe's Output:** `[/uri]` | **Group Output:** `[moon.jpg)](/uri]`

Joe's ouput is correct since it correctly contains the link within `516.md`.

The bug in my group's implementation is that the code checks for the first instance of what our group called the "pivotal sequence" or the sequence ")[" which usually leads to the beginning of a link. However, `516.md` has two instances of the pivotal sequence, the second of which actually starts the link, as the first is in the link container.
```
int firstBracket = s.indexOf("[");
int pivotalSeq = s.indexOf("](");
boolean containerGood = false;
String linkContainer = "";
//this obtains the whole container like [Link]
if (firstBracket >=0 && pivotalSeq > firstBracket)
    linkContainer = s.substring(firstBracket,pivotalSeq+1);
```
My group's code needs to check for the last index of the pivotal sequence to make the code work for `516.md`.