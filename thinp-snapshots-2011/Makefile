IMAGES=\
	test-image.svg

PDF_IMAGES=$(subst .svg,.pdf,$(IMAGES))

.SUFFIXES: .svg .pdf

.svg.pdf:
	rsvg --format=pdf -o $@ $<

talk.html: thinp-and-snapshots-talk.org $(IMAGES)
	emacs --batch --visit=$< \
	--execute='(add-to-list (quote org-export-html-inline-image-extensions) "svg")' \
	--execute='(org-export-as-html-and-open nil)'