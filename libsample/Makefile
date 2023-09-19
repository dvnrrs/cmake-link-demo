DEFAULT: libsample.so

sample.o: sample.c
	$(CC) -c -fpic $<

libsample.so: sample.o
	$(CC) -shared -o$@ $<

.PHONY: clean
clean:
	rm -f sample.o libsample.so
