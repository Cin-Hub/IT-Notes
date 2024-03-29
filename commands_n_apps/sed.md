# Sed - stream editor for filtering and transforming text
- [GNU.org - sed homepage](https://www.gnu.org/software/sed)

## Description (excerpt from man page):
> Sed is a stream editor.  A stream editor is used to perform basic text transformations on an input stream (a file or input from a pipeline).


## Links

- [sourceforge.io - sed project page](https://sed.sourceforge.io/)
- [GNU.org - sed manual](https://www.gnu.org/software/sed/manual/html_node/index.html)
- [The seder's grab bag](https://sed.sourceforge.io/grabbag)

# Basics: change string in a file

Change "foo" to "bar" from example.txt:  

```shell
sed 's/foo/bar/' example.txt
```

- _The changes will be printed to stdout, but the file itself stays the same._
- _Delimiter: The character after the `s` is the delimiter - in this case it's a slash `/`. But other characters can be used as well - for example: `.` `;` `|`_
- _foo can be a string or a regular expression._
- Only the first `foo` in each line will be changed. The syntax for all foo is `'s/foo/bar/g'` (g for global)

----

Change every "foo" to "bar" in example.txt:  

```shell
sed -i 's/foo/bar/g' example.txt
# or create a backup example.txt.bak, then change original
sed -i.bak 's/foo/bar/g' example.txt
```

# Options

|          Option           | Description                                          |
|:-------------------------:| ---------------------------------------------------- |
|            -i             | Edit files in place.                                 |
|       -i\[SUFFIX\]        | Create a backup, then edit the file.                 |
| -E, -r, --regexp-extended | Use [extended regular expressions](../misc/RegEx.md) | 


# Examples

Read the public ssh key from a file, put a string with options in front and append it to the `~/.ssh/authorized_keys` file: 
```shell
cat ~/.ssh/id_ed25519.pub | sed 's/^/no-port-forwarding,no-X11-forwarding,no-agent-forwarding,no-pty /' >> ~/.ssh/authorized_keys
```

----

Replace all "foo" with "bar" in every file in the current directory and all subdirectories:  
```shell
find ./ -type f -print0 | xargs -0 sed -i 's/foo/bar/g'
```

Command autopsy:

| Section              | Description                                                                                                                                                   |
|:-------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| find ./ -type f      | Search all files in the current directory and all subdirectories.                                                                                             | 
| -print0 \|           | Print the full file name, followed by a null character (instead of the newline character) and pipe the output to the next command.                            |
| xargs                | Build and execute the following command from the piped input.                                                                                                 |
| -0                   | Input items are terminated by a null character instead of a whitespace or newline. Quotes and backslash are not special (every character is taken literally). |
| sed -i 's/foo/bar/g' | Read each file piped by `find`, substitute all occurrences of foo with bar `s/foo/bar/g` and edit the file in place `-i`.                                     |


> [!important]
> 
> The combination of the `-print0` and `-0` option ensures, that files with whitespaces, quotes or backslashes in their name are processed correctly.