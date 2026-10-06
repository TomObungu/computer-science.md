Regular expressions are a language for matching text based of the Perl programming language. They are based on a finite state machine. Regular expressions  is also known as re, regex or regexp.

Regular expressions have a habit of getting out of hand quickly. They are a regular language and bounded in complexity. They were first introduced back in the 1950s by Stephen Cole Kleene. They are widley integrated in UNIX tools back before there were standards. By the time POSIX standardized things, there were multiple competing standards. 

# How to read a regular expression 
Regular expressions are read from the left one item at a time. 

# Syntatical Wildcards
`.` - The dot matches any character
`^` - The cartet matches the start of a line
`$` - The dollar sign matches the end of a line

## Examples
The 

# Uses of Regex
##  `grep` for search 
Grep is a search tool for text documents. It's name comes from the ed editor command. Grep stands for global/regexp (regular expressions)/print (g/re/p). It prints all lines in its input that match a regexp passed as an argument. 

A faster alternative for grep is `ripgrep`. However they don't behave the same or aren't always available. 

## Tags for `grep`
- `-i` - Case insensitive search
- `-e` or `-p` - extended or Perl (non-POSIX) regexp
- `-o` - only matching the string not line
- `-v` - inverted matching 
- `-R` - search folder recursivley 

## Examples
An example is trying to find the number of words in the English lexicon that contain double letters. 

Assuming a dictionary is stored at `/usr/share/dict/words`. It is possible to use the `grep` command and the `wc` command to 
