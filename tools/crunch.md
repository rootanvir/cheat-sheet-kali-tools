# Crunch
## Installation

```bash
    apt install crunch
```
## Visit Hydra's Github
#### Go to [Crunch repo](https://salsa.debian.org/debian/crunch) page
#### Go to [Crunch sourceforge](https://sourceforge.net/projects/crunch-wordlist/) page

---
## Documentattion
#### Read [Crunch Manual](../manual/crunch.txt)
---
# Generate wordlist 

### Usage: crunch \<min\> \<max\> [options]  
- #### where \<min>\ and \<max>\ are the minimum and maximum lengths of the generated words, respectively.
| Command                                                                 | Description                                                                                                      |
|-------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| `crunch 1 8`                                                            | Displays a wordlist starting at `a` and ending at `zzzzzzzz`.                                                     |
| `crunch 1 6 abcdefg`                                                     | Displays a wordlist using the character set `abcdefg`, starting at `a` and ending at `gggggg`.                   |
| `crunch 1 6 abcdefg\`                                                   | Uses the space at the end of the character string, either escaped with `\` or enclosed in quotes.                 |
| `crunch 1 8 -f charset.lst mixalpha-numeric-all-space -o wordlist.txt`  | Uses `mixalpha-numeric-all-space` charset and writes the wordlist to `wordlist.txt`.                             |
| `crunch 8 8 -f charset.lst mixalpha-numeric-all-space -o wordlist.txt -t @@dog@@@ -s cbdogaaa` | Generates an 8-character wordlist starting at `cbdogaaa` and ending at `"dog"`.                                   |
| `crunch 2 3 -f charset.lst ualpha -s BB`                                 | Generates a wordlist starting from `BB` and ending at `ZZZ`.                                                      |
| `crunch 4 5 -p abc`                                                     | Generates permutations like `abc`, `acb`, `bac`, `bca`, `cab`, `cba`.                                           |
| `crunch 4 5 -p dog cat bird`                                             | Generates permutations like `birdcatdog`, `birddogcat`, `catbirddog`, etc.                                       |
| `crunch 1 5 -o START -c 6000 -z bzip2`                                  | Generates compressed `bzip2` files with 6000 words each. File names are `first_word-last_word.txt.bz2`.           |
| `crunch 4 5 -b 20mib -o START`                                          | Generates 4 files with sizes of 20MB each (except the last, which is 11MB).                                      |
| `crunch 3 3 abc + 123 !@# -t @%^`                                       | Generates 3-character words with specific character types in a specific order (lowercase, number, symbol).      |
| `crunch 3 3 abc + 123 !@# -t ^%@`                                       | Generates 3-character words starting with `!1a` and ending with `#3c`.                                           |
| `crunch 4 4 + + 123 + -t %%@^`                                          | Generates words from a set of character types (letters, numbers, symbols).                                      |
| `crunch 5 5 -t ddd@@ -o j -p dog cat bird`                              | Permutes the words `dog`, `cat`, `bird` in combination with `ddd@@`.                                             |
| `crunch 7 7 -t p@ss,%^ -l a@aaaaa`                                      | Treats the `@` symbol as a literal, generating words like `p@ssA0!`, `p@ssA0@`, etc.                            |
| `crunch 5 5 -s @4#S2 -t @%^,2 -e @8 Q2 -l @dddd -b 10KB -o START`       | Generates wordlist with specific start and end strings, broken into 10KB files.                                  |
| `crunch 5 5 -d 2@ -t @@@%%`                                             | Generates words with exactly 2 lowercase characters, starting from `aab00` and ending at `zzy99`.                |
| `crunch 10 10 -t @@@^%%%%^^ -d 2@ -d 3% -b 20mb -o START`              | Generates 10-character words with specific formats, written to 20MB files.                                       |
| `crunch 8 8 -d 2@`                                                      | Generates 8-character words with no more than 2 lowercase characters, starting from `aabaabaa` to `zzyzzyzz`.   |
| `crunch 4 4 -f unicode_test.lst japanese -t @@%% -l @xdd`               | Loads Japanese characters from a charset file, generates words like `@日00` to `@語99`.                           |

# Crunch Command Guide




## Length Parameters: `8 8`
- **First number (8)**: Minimum length of the generated words.
- **Second number (8)**: Maximum length of the generated words.

  Example: 
  - `crunch 8 8` will generate words that are exactly 8 characters long.

## Other Key Parameters

### Charset: `abcdefg`
- Specifies the character set to be used for generating words.
  - Example: `crunch 1 6 abcdefg` will generate words using the characters `a, b, c, d, e, f, g`.

### File Options: `-o wordlist.txt`
- Specifies the output file where the wordlist will be saved.
  - Example: `crunch 1 6 -o wordlist.txt` will save the output to `wordlist.txt`.

### Charset List File: `-f charset.lst`
- Loads a predefined charset from a file. 
  - Example: `crunch 1 8 -f charset.lst mixalpha-numeric-all-space` uses a charset from `charset.lst`.

### Character Substitution: `-t @@dog@@@`
- The `-t` option uses a **template** for word generation. Each `@` is replaced by a random character from the charset.
  - Example: `crunch 8 8 -t @@dog@@@` will generate words like `xxdogxxx`.

### Start String: `-s cbdogaaa`
- Specifies the **start string** for generating the wordlist. This allows you to start at a particular word.
  - Example: `crunch 1 8 -s cbdogaaa` will start generating words from `cbdogaaa`.

### Output Compression: `-z bzip2`
- Compresses the output using the specified method (like `bzip2`, `gzip`, `lzma`).
  - Example: `crunch 1 5 -o START -c 6000 -z bzip2` generates a compressed `bzip2` file with 6000 words per file.

### Wordlist Splitting: `-b 20mib`
- Splits the generated wordlist into smaller files of the specified size (in megabytes).
  - Example: `crunch 4 5 -b 20mib -o START` will split the wordlist into 20MB files.

### Permutations: `-p dog cat bird`
- Generates **permutations** of the specified words.
  - Example: `crunch 4 5 -p dog cat bird` will generate `dogcatbird`, `birddogcat`, etc.

### Placeholder: `+`
- The `+` symbol is a **placeholder** for any character set.
  - Example: `crunch 3 3 abc + 123 !@#` will generate combinations of lowercase letters, numbers, and symbols.

### Literal Characters: `-l`
- Treats the specified characters as **literal** instead of substituting them.
  - Example: `crunch 7 7 -t p@ss,%^ -l a@aaaaa` will treat the `@` as a literal symbol.

---

## Putting It Together

Example: `crunch 8 8 -f charset.lst mixalpha-numeric-all-space -o wordlist.txt -t @@dog@@@`
- **8 8**: Generate words that are exactly 8 characters long.
- **`-f charset.lst mixalpha-numeric-all-space`**: Use the character set `mixalpha-numeric-all-space` from the file `charset.lst`.
- **`-o wordlist.txt`**: Save the generated wordlist to `wordlist.txt`.
- **`-t @@dog@@@`**: Use the template `@@dog@@@`, where `@` is a placeholder for any random character, and generate words based on this template.
