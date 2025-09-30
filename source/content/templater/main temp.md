<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title");
    await tp.file.rename(title);
  } 
  tR += "---"
%>
title:  <%* tR += title %>
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
updated: <% tp.file.last_modified_date("YYYY-MM-DD HH:mm") %>
tags: 

---
# <%* tR += title %>
<%* app.workspace.activeLeaf.view.editor?.focus(); %>