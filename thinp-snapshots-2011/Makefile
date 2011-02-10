DOCUMENTS=\
	thinp-and-snapshots-talk.html

all: $(DOCUMENTS)

IMAGES=\
	test-image.svg

PDF_IMAGES=$(subst .svg,.pdf,$(IMAGES))

.SUFFIXES: .svg .pdf .org .html

.svg.pdf:
	rsvg --format=pdf -o $@ $<

.org.html: $(IMAGES)
	emacs --batch --visit=$< \
	--execute='(add-to-list (quote org-export-html-inline-image-extensions) "svg")' \
	--execute='(org-export-as-html-and-open nil)'
	sed -ie 's/<img src=\("[^"]*.svg"\)/<object data=\1 type="image\/svg+xml" id="svg"/g' $@