---
alias: {{value:title}}
tags: [goal, {{value:tags}}]
type: {{value:lifestyle,analytical,athletic,professional,creative}}
target: {{value:target}}
progress: 0
timespan:
---
%% Bar:: `$= dv.view('progress-bar', {file: '{{DATE}}_{{VALUE:title}}'})`%%

# {{value:title}}

# Description
{{value:description}}

## What does success look like? What are the key results?
- 

## Related core values
- 

## Projects to make this happen
### Ideas
- 

### Created projects
```dataviewjs
const pages = dv.current().file.inlinks.where(p => dv.page(p.path).tags?.contains('project'));

dv.table(["Project", "Status"], pages.map(p => {
	const page = dv.page(p.path); 
	return [page.file.link, page.status]
}));
```