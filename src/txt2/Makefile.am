if XMLTOTXT

CLEANFILES = gphoto2.txt2

txt_DATA = gphoto2.txt2

# FIXME: detect software presence, disable build if necessary
SED = /bin/sed

gphoto2.txt2: $(gphoto2xml)
	$(XMLTO) html-nochunks -o . $<
	$(SED) 's$$<a href="\([^#][^"]*\)"[^>]*>\([^<]*\)</a>$$\2 [\1]$$g' < gphoto2.html > $@.tmp
	$(W3M) -T text/html -cols 78 -dump $@.tmp > $@ || (s=$$?; rm -f $@; exit $$s)
	rm -f $@.tmp gphoto2.html

endif
