all : mapmake makecv  makecomp map.h
#7.h 0.h

makecomp : makecomp.o
	gcc -o $@ $^ -lz

mapmake : mapmake.o
	gcc -o $@ $^

makecv : makecv.o
	gcc -o $@ $^

%.h : %.gz
	./makecv < $^ > $@

%.gz : %.uncompress makecomp
	./makecomp < $^ > $@

%.uncompress :
	./mapmake $@ > $@

clean :
	rm -rf mapmake makecv *.h *.gz *.uncompress *.o *~

