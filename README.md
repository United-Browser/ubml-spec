# United Basic Markup Language (UBML) specification

## 1. Introduction

The United Basic Markup Language (UBML) is a lightweight markup language with an easy-to-understand syntax and rich content representation. This specification outlines the structure, syntax, and elements supported by UBML.

## 2. Syntax and structure

Elements are defined using the equal sign (=) followed by the element name and any required or optional attributes. 

```ubml
=element[[:attribute]] [data]...
```

This structure breaks down as follows:

- element: The name of the element, such as =text, =h1, or =image.
- [:attribute] (optional): An optional attribute for the element, such as :c++ or :php for =code elements.
- [data] (optional): The data associated with the element, which could be parameters, content, or both, depending on the specific element. This section may span multiple lines.

A few examples to quickly grasp the concept of the United Basic Markup Language:

```ubml
=h1 A heading
=text Some text content.
=image ntd://smfw2f923jf80 An image with this caption
=code:js console.log('Hello World')
```

Some elements, such as image, video, audio and embed, can take multiple lines of data to combine items in a slideshow or playlist. Read further for the specification of the elements including examples.

## 3. Elements

### 3.1 Metadata

These elements contain information about the UBML page.

#### `=ubml [version]`
UBML page declaration/version.

#### `=title [title_text]`
Title of the UBML page.

#### `=description [description_text]`
Description of the UBML page.

#### `=path [path]`
Path of the page. The path element can be used to define its relationship to other UBML pages.

### 3.2 Content

#### `=text [content]`
Basic text block that allows you to write paragraphs and inline text. It supports basic markdown syntax for formatting, which includes:

- \*Italic\*: Enclose text with a single asterisk (\*) to make it italic. For example, \*italic text\* will be displayed as *italic text*.
- \*\*Bold\*\*: Enclose text with double asterisks (\*\*) to make it bold. For example, \*\*bold text\*\* will be displayed as **bold text**.
- \*\*\*Bold Italic\*\*\*: Enclose text with triple asterisks (\*\*\*) to make it bold and italic. For example, \*\*\*bold italic text\*\*\* will be displayed as ***bold italic text***.
- \[Links\](url): To create a link, enclose the link text in square brackets (\[]) and immediately follow it with the URL in parentheses. For example, \[United\](https://www.united-browser.com) will be displayed as [United](https://www.united-browser.com).

These basic markdown formatting options can be used within the [content] section of the =text element to style the text as needed. Remember that the [content] section can span multiple lines, if needed.

#### `=h1 [header_text]`
The =h1 element is used to create the largest heading in your UBML document. It is typically used for main titles and section headers. The [header_text] is the content of the heading and can be any text you wish to display.

#### `=h2 [header_text]`
The =h2 element is used to create a large heading in your UBML document. It is typically used for subheadings within main sections. The [header_text] is the content of the heading and can be any text you wish to display.

#### `=h3 [header_text]`
The =h3 element is used to create a medium-sized heading in your UBML document. It is typically used for subheadings within subsections. The [header_text] is the content of the heading and can be any text you wish to display.

#### `=h4 [header_text]`
The =h4 element is used to create a small heading in your UBML document. It is typically used for subheadings within smaller sections or for emphasizing specific topics. The [header_text] is the content of the heading and can be any text you wish to display.

#### `=h5 [header_text]`
The =h5 element is used to create the smallest heading in your UBML document. It is typically used for the least important subheadings or for further emphasis on specific topics. The [header_text] is the content of the heading and can be any text you wish to display.

#### `=list [list_items]`
The =list element is used to create unordered or ordered lists in your UBML document. The [list_items] is the content of the list. To create an unordered list, start each list item on a new line with a hyphen (-) followed by a space. To create an ordered list, start each list item on a new line with a number followed by a period (1.) and a space.

##### Example of an unordered list
```ubml
=list
- First item
- Second item
- Third item
```

##### Example of an ordered list
```ubml
=list
1. First item
2. Second item
3. Third item
```

#### `=markdown [markdown_content]`
The =markdown element is used to create a section within your UBML document that supports full Markdown syntax. This allows you to use the extensive features of Markdown to format your content, including headings, lists, blockquotes, code blocks, tables, and more. The [markdown_content] is the content of the Markdown section and can include any text you wish to display, formatted using standard Markdown syntax. Some of the key features of Markdown syntax that you can use within the =markdown element include:

- Headings: Use one or more hash symbols (#) followed by a space to create headings of various sizes. For example, "# Heading 1" creates the largest heading, while "## Heading 2" creates a slightly smaller heading, and so on.
- Lists: Use hyphens (-) or numbers followed by periods (1.) to create unordered or ordered lists. For example, "- Item 1" creates an unordered list item, while "1. Item 1" creates an ordered list item.
- Blockquotes: Use a greater-than symbol (>) followed by a space to create blockquotes. For example, "> This is a blockquote" creates a blockquote.
- Code blocks: Use triple backticks (\```) to enclose a code block. Optionally, you can specify a language identifier immediately after the opening backticks for syntax highlighting. For example, "\```javascript" creates a JavaScript code block.
- Tables: Use pipes (|) and hyphens (-) to create tables. For example, "| Header 1 | Header 2 |\n| -------- | -------- |\n| Cell 1   | Cell 2   |" creates a simple table with two columns and two rows.

Remember that the [markdown_content] section can span multiple lines, if needed. For a more comprehensive guide on Markdown syntax, you can refer to the official documentation or popular Markdown guides available online.

#### `=quote [quoted_content]`
The =quote element is used to create blockquotes in your UBML document. It is typically used to display quoted text or content that should be set apart from the main body of text. The [quoted_content] is the content of the blockquote and can be any text you wish to display. This content can span multiple lines, if needed.

#### `=rule`
The =rule element is used to create a horizontal rule in your UBML page. It is typically used to visually separate sections or topics within the document. There is no additional content or parameters required for this element.

#### `=// [comment]`
The =// element is used to add a comment to your UBML document. The [comment] is the content of the comment and will not be rendered in the final output.

#### `\\=[escaped_element]`
Any character that precedes an element on the same line prevents the element from being rendered. However, to explicitly escape elements, the `\=` syntax is recommended.
