# Project overview
This project is a plugin for Calibre that finds translation/corruption issues in ePub files, grades them on how corrupted they are, and fixes some tedious issues.

# Project deliverables
## File grading
It should be able to popup a window containing a report detailing issues it found so that they may be assessed by a reader with a summary at the top.

Issues for example:
- Line breaks in the middle of a sentence
- letters being mistaken, such as 'h' becomes 'fi'
- Multiple chapters joined together causing issues indexing with low-memory e-readers
- Inconsistent fonts
- Misspelled words (must accept GB and US English)

## Fixing Formatting Errors
It should be able to:
- Automatically split the book into chapter files
- Correctly make a table of contents

## Fix styling errors
It should be able to unify the fonts used to a consistent body and a title font, with a stylesheet so that it can be repacked into an epub afterwards

## Fixing Reading Errors
It should make a dialogue box showing every spelling mistake it finds (with context of the words either side) and allow the user to choose replacements or skip them.

# Out of scope
- There will be no LLM or AI integration to automatically fix reading errors
- It will not have to handle file formats other than Epub
- Books only need to be processed individually, bulk processing is not necessary

## Assumptions & constraints
- The code will be run through Calibre as a plugin with access to metadata and book files
- External Python libraries can be used