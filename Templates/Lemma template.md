<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>
# Lemma: <%* tR += `${title}` %>

**Type:** #lemma  

## Statement
<% tp.file.cursor() %>

## Proof (optional)


## Used In


## Related Lemmas

