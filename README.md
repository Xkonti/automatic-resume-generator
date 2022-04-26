# Automatic Resume Generator

Automatically generate a PDF resume from a Markdown file.

Whenever the `resume.md` file is updated (push), the PDF version is automatically generated via a Github Action. That PDF file is then used to automatically create a Github release. Each branch has it's own set of releases so that branches can be used to maintain multiple versions of your resume. If the resume.md file is updated within a single day the corresponding release is updated to limit the number of releases.

# Page break

When converting Mardown to PDF it's hard to tell when the next page will begin. Using page breaks in CSS doesn't work well. Because of that you can use some trial and error to find the best spot to for example insert a heading that will be the top of the next page:

```md
Experience (continued)
----------------------
```

# Additional empty lines

You can force markdown to add an empty line by inserting the `<br/>` tag. This might be useful when you want the header to align with the top of the next page:

```md
<br/>

Technical expertise
-------------------
```

# How?

The Node.js `md-to-pdf` library is used to combine the markdown file with a custom CSS stylesheet: https://github.com/simonhaenisch/md-to-pdf