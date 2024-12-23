# Quiz Questions

Prior to 2024 the book used Jupyter Quiz, which is based on JSON files. These are easy to set up and use, but don't work properly when a book page uses the interactive mode of Sphinx-Thebe. Therefore, the quiz questions were converted to H5p.

To make the change transparent, and possible support future conversion in case H5p is no longer supported, the following actions were taken:
1. A tag was added to the import statement in the Python cell, `# jupyterquiz-import`. If all exercises in a page are converted, the entire cell can be commented out (but should remain in the notebook with cell tag `remove-input`)
2. A cell containing a Jupyter Quiz exercises should have a tag of the form: `# jupyterquiz-exercise-x-y-z` where `x`, `y`, and `z` are the chapter, section, and exercise numbers (as they appeared in the original book and Jupyter Quiz question number), respectively. This tag should be added to the cell containing the exercise prompt, and the cell tag `remove-input` should remain in place.
3. H5p exercises are created and stored in... SHIYA FINISH THIS!