# The *toctree* related question
## What options are available for the *toctree*?
 In Sphinx, the `toctree` directive is used to include a table of contents in your documentation. This directive is useful for creating a hierarchical structure within your documentation by specifying which documents should be included in the table of contents.

The `toctree` directive has several options that you can use to customize its behavior. As of the version up to October 2023, here are the main options for the `toctree` directive:
1. **:caption:**
2. The `caption` option in a Sphinx `toctree` directive allows you to provide a title for the table of contents that the `toctree` generates. This caption will be rendered as a heading above the table of contents in the output documentation.
3. **:maxdepth:** 
   - Specifies how many levels of the hierarchy to include in the table of contents. For example, `:maxdepth: 2` includes the first two levels.

4. **:glob:** 
   - Allows the use of wildcard patterns to include multiple documents that match the given pattern. For example, `:glob:` would include all documents that match the specified pattern.

5. **:hidden:**
   - If set, the specified documents will be listed in the toctree but will not be displayed in the table of contents.

6. **:titlesonly:**
   - When set, only the titles of the included documents will be shown in the table of contents, rather than including the entire hierarchy.

7. **:reversed:**
   - When this option is set, the order of the documents in the table of contents will be reversed.

Here’s an example of how you might use the `toctree` directive in a reStructuredText file:

```rst
.. toctree::
   :maxdepth: 2
   :glob:
   :hidden:
   :titlesonly:
   :reversed:

   intro
   tutorial/*
   reference/*.rst
```

This directive will create a table of contents that includes the specified documents, limiting to two levels deep, including titles only, and applying the specified patterns.

## Can I have a mutiple *toctree* in my Sphinx document?
However, keep in mind that having multiple `toctree` directives in the same document may lead to redundancy or confusion if they're not clearly delineated in terms of purpose and structure. Each `toctree` should serve a distinct function in organizing your documents.

Here’s an example of how you can use multiple `toctree` directives:

```rst
.. toctree::
   :maxdepth: 1
   :titlesonly:

   introduction
   installation
   usage

.. toctree::
   :maxdepth: 2
   :titlesonly:

   advanced_topics
   tutorials/*
```

In this example:

- The first `toctree` includes links to the `introduction`, `installation`, and `usage` documents.
- The second `toctree` focuses on `advanced_topics` and includes all documents in the `tutorials` directory, showing a broader depth level.

When using multiple `toctree` directives, be mindful of how they affect your content's structure and navigation. It's generally good practice to keep a clear hierarchy and logical organization in your documentation.
