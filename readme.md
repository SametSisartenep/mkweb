# mkweb

Mkweb is a very little framework I've developed for the last four
years based on markdown files.
It started as an actual `mkfile` (of which there was a `Makefile`
translation for UNIX™ systems) and turned into a standalone
[rc(1)](http://man.9front.org/1/rc) script over time.

I've been meaning to release it for a long time now.

_I know there are many like it, but this one is mine_.

## Usage

The script is quite simple and, since you will have to modify it
whether you want to or not, I recommend you take a peek before we
continue.

Alright, see?  there are three variables you need to keep track of:
`filter`, `sections` and `site`.  The `filter` is a
[regexp(6)](http://man.9front.org/6/regexp) used to exclude files from
`sections`, a list of folders possibly holding an `index.md`, which
would otherwise crawl into the depths of every directory there is.
`site` is the root URL of your website, it's only used for generating
the sitemap file (ab)used by some bots out there.

Every time you create a section and add an `index.md` to it, you must
run `mkweb` to generate the entire site, or you can also just `mkweb
-s path/to/newsection` to process your new webshit.

This process will translate the markdown file into html, while
attaching to it a head, a menu and some feet (see `tpl/`) to make a
proper document.

And that's it.  All the hypertexting is done by yiyus' `md2html.awk`,
which could be replaced by discount or any other translator of your
choice, doesn't even need to be a markdown one (Wikitext, AsciiDoc,
BBCode are all easy to plug in).

Enjoy!
