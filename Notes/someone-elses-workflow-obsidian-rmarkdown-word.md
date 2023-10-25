

https://www.reddit.com/r/ObsidianMD/comments/124cd8y/my_setup_as_a_researcher_how_to_write_run/

I am a researcher, and a lot of what I do is analyzing data and writing papers. Below the setup I use to write papers and collaborate with others who are using other software.

So some things I needed my setup have are:

1. Zotero integration. I have been using Zotero ([https://www.zotero.org/](https://www.zotero.org/)) daily for more than 10 years now.
    
2. I didn't want to use Microsoft Word, as I use Linux. Wine (compatibility layer that allows you to run Windows software in Linux) cannot support it as well as I wanted (there are multiple bugs with MS office, and especially when you want it to integrate with Zotero... I'd have to run Zotero with Wine too), so I have to boot up a virtual machine inside Linux to work every day.
    
3. R and Rstudio. I use R for my statistical analysis, and I primarily run it through Rstudio. Now lately I have started using Rmarkdown to also write, as I can use inline code blocks and have it produce outputs of statistical analyses right into a paragraph of text (e.g. "the mean age of the participants was X ± Y", and the X and Y would actually be R code that would print the output in line, thereby reducing the chance for copy-pasting mistakes, and would automatically change output if I change anything in the analysis). In addition, Zotero integrates beautifully with Rstudio and Rmarkdown, so I can literally write an entire scientific paper in RStudio without needing to ever use Word.
    
4. Be able to output in MS Word. A problem that came up a lot in my setup over the years is dealing with senior collaborators. During my PhD I wanted to switch to using LibreOffice or even using the online MS Word, and senior professors would tell me to send them a MS word file (docx), without compromising. What I can do now is write things in Rmarkdown and have knitr output everything into a docx, which I send them, they send me back their tracked changes, I integrate them manually in the Rmarkdown, and produce the next version. I actually prefer to integrate things manually instead of pressing "accept changes", because many times I don't agree with all changes, and integrating things manually makes me re-think of the change and get better ideas.
    
5. I want to use Obsidian for writing. This is because I love markdown, and I also use syncthing ([https://syncthing.net/](https://syncthing.net/)) to sync my Obsidian library with my laptop, my phone, and my desktop, so wherever I am I can pop open my laptop or phone, work on a paper a bit or add quick notes, and have them update everywhere. Then, when I sit down to do some deep writing on my desktop, I can use my multi-screen setup to open 4-5 windows of the same document in different places.
So, how to make all that work seamlessly?

One problem is that Obsidian cannot view Rmarkdown files (.Rmd), and RStudio does not recognize markdown files (.md) as Rmarkdown, even though it may contain R code blocks. A solution I found is I modified the Obsidian plugin 'txt as md' ([https://github.com/deathau/txt-as-md-obsidian](https://github.com/deathau/txt-as-md-obsidian)) to also add more filetypes, including Rmd. Once you do that, Obsidian can easily open and work with .Rmd files as if they are native md files.

Another problem is that no matter how much I tried, the two available Zotero plugins for Obsidian do not work for me (this [https://github.com/mgmeyers/obsidian-zotero-integration](https://github.com/mgmeyers/obsidian-zotero-integration) and this [https://github.com/hans/obsidian-citation-plugin](https://github.com/hans/obsidian-citation-plugin)). I am not sure if that is because I'm on Linux, but they just don't work. However, RStudio on Linux works great with Zotero, and I can easily add citations using the Better BibTeX for Zotero plugin ([https://github.com/retorquere/zotero-better-bibtex](https://github.com/retorquere/zotero-better-bibtex)) to create citation keys. That way, I can simply copy/paste the citation key (e.g. '@lastname2020') in the text and have it render into the citation when I render the file in Rstudio. I sometimes write documents with > 300 references, and with Zotero running in a Windows VM trying to refresh a huge word document takes a long time, and would lead to corrupt citations. That's no problem with a markdown/Rmarkdown document.

Want to run huge mixed-effects models, meta analyses, and use the power of tidyverse within Obsidian? Easy! Want your document to have over 300 references and not slow down your PC when you want to change a reference? Easy! If you are advanced, as you are basically working with markdown text, this setup allows you to use version control through git, which is way more powerful than any version control Word offers. If you are REALLY advanced, you can easily open this document and edit rapidly with other code/text editors (I use Kate in Linux, but you can edit it with Emacs or Vim).

So now what I do is:

1. I create a new markdown file in Obsidian in the folder that I want.
    
2. Click on the file and "Show in system explorer"
3. Change the file extension to '.Rmd'. Now it's a Rmarkdown file
    
2. Write and work on the data analysis and the text. I can now add references through the citation keys (e.g. '@lastname2020') and add R code blocks to have my statistical analysis AND the journal article for the project all in one place. Again that allows me to work a) from Linux b) with Obsidian and all its plugins and the multi-screen editing of the same document, c) from my phone, d) with markdown, e) with Zotero, f) use git, Github, Gitlab etc for the best version control possible, g) rapid backup and sync to all my devices using syncthing.
    
3. Use RStudio to run the statistical analysis and render to docx. That allows me to send a docx to senior professors, integrate their changes, and keep using the ease and power of R and Obsidian to work.
    
4. When I want to submit the paper to a journal, I render again to docx, change the formatting according to what the journal wants, and submit. Rstudio also has packages like papaja ([https://github.com/crsh/papaja](https://github.com/crsh/papaja)) which allow you to format an Rmarkdown easily for journal articles.
    

So this is how I did it. Any ideas I'd love to hear. I wanted to share in case someone (like me a few years ago) would find this useful.