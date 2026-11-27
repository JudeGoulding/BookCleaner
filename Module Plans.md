# UI
2 buttons:
- Grade selected book
- Clean selected book
Report
- Error list
Dialogue boxes
- Spelling/dict check
# File Grading
- ebooklib python library allows the accessing of raw HTML from epub contents
- Could use Regex to search for specific things and tags
## Infractions:

| Type                                      | Score                                                          | Description                                                             | Example                                                                         |
| ----------------------------------------- | -------------------------------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Multiple chapters inside a file           | `+n` where n is number of chapters already present in the file |                                                                         | File 1 contains chapters 1, 2 and 3 when they should have individual files each |
| Line break in a sentence                  | +1                                                             |                                                                         | When the next<br>       paragraph starts in the middle of a sentence            |
| Spelling Errors ( after use consultation) | +2                                                             |                                                                         |                                                                                 |
| Extraneous font                           | +3                                                             | Heading class uses multiple sized, or body fonts and sizes inconsistent |                                                                                 |
| Speech grammar issue                      |                                                                | Starting a sentence with speech should be a new line                    | ...sentence. "Speech," he said. The text carries on...                          |
# File Fixing
## Spelling checker
- Uses pySpellchecker library to collate a list of unknown words and return it
## Spelling reporter
- Takes results of spelling checker, plus the most likely word for each mistake
- Displays a table of the wrong word (with 2 words of context), and an editable box with the most likely word prepopulated.
- Has a button to dismiss a word on each row
- Button at the bottom to Accept or Skip
- Writes to the buffer copy of the book with the user's choices
## Chapter splitting
The final step, checks for chapter names or headings, then writes a new file for each with the chapter name
## Contents page making
Steps through the file name and makes a contents page:
- Intro
- Prologue
- Chapter 1
- ...
- Chapter X
- Epilogue
## Line break fix
Checks for paragraph tags not having punctuation before them
## Font unifying
Creates two lists, one for Body fonts and one for Title. Does the same for Sizes. Picks one and updates each type of text to be unified.
## Stylesheet maker
Adjusts a standard template to suit the new book if need be. Fonts and sizes will be part of this template.