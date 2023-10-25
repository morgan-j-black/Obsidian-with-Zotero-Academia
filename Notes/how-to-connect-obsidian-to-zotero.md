Tutorial notes for my Zotero to Obsidian (and RMarkdown) writing workflow.
# Zotero

Have this program (Zotero) installed and full of "all your things" ideally.  All good if you have not done this yet. You may not yet be a full Zotero convert yet.
## Plugins
Required Zotero add-on:  "Better Bibtex"
Follow these instructions to add this plug in to Zotero
[https://retorque.re/zotero-better-bibtex/installation/

Recommended Zotero add-on: "Zotfile" - not required for today, but excellent for managing pdfs.  I like to have this addon automatically copy and rename downloaded pdfs with a useful, consistent format into a specified articles folder.  This serves as a backup and can be very handy when trying to locate an article to share or if you have a reference manager issue and need to reload a nice, tidy library. Mendeley and MSWord both have corrupted my reference library on multiple occasions.  This was one of the main reasons I first switched to Zotero and have since come to love it more because it works so well with so many other useful programs.

## Getting Zotero ready...
1. Ensure you have install the Better BibTex addon (instructions above)
2. Set Better Bibtex preferences (optional)
	1. Found under Tools now in Zotero
	2. efault settings are likely good, but know that they are there. For example, you might prefer citekeys in a different format that you are used to remembering
4. Export library from Zotero
	1. Ensure you have selected (are currently looking at) your whole Zotero Library (My Library)
	2. Select File > Export Library
	3. Format is "Better Bibtex"  (not any of the other similar looking ones )
	4. Ensure you choose automatic update option "Keep updated"![[Pasted image 20231025121848.png]]
	5. When prompted for location of where to export this libary, choose you main Obsidian Vault folder.
	6. Give it a simple names without spaces or capitals, followed by the file extension .bib.  Examples: library.bib or zotero.bib or zotero_library.bib ![[Pasted image 20231025121956.png]]


That's all for Zotero.  Magic will happen soon!  :)

### Now open/navigate back to Obsidian...

# Citations plugin template

Notes on the template below:
"{{title}}"  The quotations here is a simple workaround to prevent special characters in article titles from making the YAML in obsidian note 'cranky'

You can add other bits of content as you like from Zotero's available metadata.

<% %> this funny notation is used with the Templater community plugin. It can be very useful for automating all kinds of things. (WARNING: rabbit hole)

The double colon after Topics is not a typo.  That makes gives the content that follows special, query-able properties.

Feel free to add or change any headers or prompts to make this all more useful to you.  This is all done in the Citations plugin Options page.

---
Title: "{{title}}"
Type: {{entry.type}}
Citekey: {{entry.id}}
<% tp.user.paper_yaml("{{entry.type}}", "{{authorString}}",  "{{year}}", "{{DOI}}") %> 
---

[Zotero]({{zoteroSelectURI}}) <% tp.user.doi_or_url('{{DOI}}' , '{{URL}}') %> 

Topics:: 

{{abstract}}
# methods:
- 

# key findings:
- 

# thoughts:
---



