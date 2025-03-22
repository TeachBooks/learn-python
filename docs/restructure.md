# Restructuring the book

Notes from Shiya and Robert early 2025 when chapters were broken down into smaller chapters and sections.

- names of subdirectories changed from numbers to single words (e.g., `01` becomes `basics`), where the "home" page of that chapter has the same name and is located in the root directory of the book. For example, see `./book/basics.md` and `./book/basics/<subpages>.md`
- Each chapter contains subdirectories `Exercises/` and `nutshell/` at minimum.
- Each nutshell chapter should have an identical file structure with subpage names to the main chapter
- Jupyter Quiz questions were converted to h5p questions. This is preseved with commented code in the subpage where the h5p exercise has been moved to.
- Small "checks" are kept on subpages, but bigger "exercises" are preserved on a final subpage in the chapter.
- Exercises/checks will be numbered using the automatic numbering of jupyter book and naming it "exercise" in the heading (e.g., `### Exercise` renders as "1.2.3 Exercise").