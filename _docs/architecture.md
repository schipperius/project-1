---
layout: page
title: Architecture
---

_pages/       → standalone pages
_posts/       → chronological blog entries
_stories/     → custom collection
_docs/        → architecture documentation
_data/        → structured YAML data
_includes/    → components
_layouts/     → wrappers


In plain English: title=page.name means: 
  “Take the value stored in name from this page’s front matter and pass it into the include under the variable name title.”
  Let’s break it down slowly. 
  You have this in your front matter: name: "Cracker Jack" Inside Jekyll, that becomes: page.name
  Now in your layout, you write: {% include lead-section.html title=page.name %} That means: 
  Look at this page. Get the value of name. When rendering the include, create a variable called title. Set title equal to that value.
  So inside the include file, this: {{ include.title }} Will output: Cracker Jack
