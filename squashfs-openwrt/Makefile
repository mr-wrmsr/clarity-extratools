INCLUDEDIR = .

LZMAPATH = lzma-4.32/C/7zip/Compress/LZMA_Lib

CFLAGS := -I$(INCLUDEDIR) -D_FILE_OFFSET_BITS=64 -D_LARGEFILE_SOURCE -O2

all: clarity-unsquashfs-openwrt

clarity-unsquashfs-openwrt: unsquashfs.o liblzma.a
	$(CXX) unsquashfs.o -L$(LZMAPATH) -llzma -o $@

liblzma.a:
	$(MAKE) -C $(LZMAPATH)

clean:
	rm -f *.o
	rm -f clarity-unsquashfs-openwrt
