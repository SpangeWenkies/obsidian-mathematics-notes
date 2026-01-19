<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>
# Definition: <%* tR += `${title}` %>

**Type:** #definition  

## Definition
<% tp.file.cursor() %>

## Intuition (optional)


## Equivalent Formulations (optional)


## Related Concepts

