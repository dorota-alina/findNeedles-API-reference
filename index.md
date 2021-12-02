# findNeedles API

## API description

`findNeedles` method counts and logs how many times particular `needles` (words) occur within a `haystack` (plaintext file) unless there are more than five `needles` with the `heystack`, in which case the method exits with an error message.
 
## Sequence of operations

1. `findNeedles` checks if the size of the `needles` array is greater than five.
2. Depending on the outcome
   * If greater than five, it output an error message and exites.
   * If smaller or equal five, it proceeeds to step 3.
3. It uses the `split` function to divide the input string using the following literals: `"`, `'`, `t`, `n`, `b`, `f`, `r`

\" double quotes character
\' single quote character
\t tab space character
\n new line character
\b back space character
\f form feed character
\r carriage return character

## Calling the method

```java
public static void findNeedles(String haystack, String[] needles) {
   if (needles.length > 5) {
       System.err.println("Too many words!");
   } else {
       int[] countArray = new int[needles.length];
       for (int i = 0; i < needles.length; i++) {
           String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
           for (int j = 0; j < words.length; j++) {
               if (words[j].compareTo(needles[i]) == 0) {
                    countArray[i]++;
                }
            }
        }
        for (int j = 0; j < needles.length; j++) {
            System.out.println(needles[j] + ": " + countArray[j]);
        }
    }
}
```

## Parameters

## Response

Method can return an output
Current code logs output in the console, alternatively an array containing the list of outputs can be returned.

It then splits the haystack string over a number of characters (including single and double quotes, tabs, newlines, word boundaries, form feeds and carriage returns) into an array of words called words.

Each "needle" (element of the needles array) is compared to each element of the words array and if a "needle" is encountered as an element of the words array, a "counter" for the respective needle is incremented.

After the search, each needle is displayed along with the number of times it occurred in the haystack.

The function then exits.

You can use the [editor on GitHub](https://github.com/dorota-alina/findNeedles-API-reference/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dorota-alina/findNeedles-API-reference/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.