<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>
# Theorem: <%* tR += `${title}` %>

**Type:** #theorem  

## Statement
<% tp.file.cursor() %>

## Proof Idea (optional)


## Consequences / properties


## Related Definitions

