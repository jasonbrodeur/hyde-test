---
layout: page
title: Customization notes
permalink: notes.html
---

### What I did to make About page work: 
- Added another item in the front matter of About page: ```permalink: about.html```
- Now it looks like: 
```
---
layout: page
title: About
permalink: about.html
---
```
you'll have to do something similar with all additional pages that have layout 'page' (not with index.html, though).

- Modified ```/_layouts/sidebar.html``` to comment out 
  - ```<!-- <a class="sidebar-nav-item{% if page.url == node.url %} active{% endif %}" href="{{ node.url }}">{{ node.title }}</a> -->``` 
- and replace it with 
  - ``` <a class="sidebar-nav-item{% if page.url == node.url %} active{% endif %}" href="{{ site.baseurl }}{{ node.permalink }}">{{ node.title }}</a``` 
- Also, commented out line ```<!-- <a class="sidebar-nav-item" href="{{ site.github.repo }}/archive/v{{ site.version }}.zip">Download</a> -->``` to remove Download link.  
- and commented out line: ```<!-- <span class="sidebar-nav-item">Currently v{{ site.version }}</span> -->``` to remove version information. 
