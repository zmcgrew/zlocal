
sed 's|-O0|-Os|g' -i "Make.defaults" || true &&
#sed 's|-rpath=$(TOPDIR)/src/|-rpath=$(libdir)|g' -i "src/test/Makefile" || true &&
make libdir="/usr/lib/" bindir="/usr/bin/" mandir="/usr/share/man/" includedir="/usr/include/" V=1 -j1 &&
prepare_install &&
make -j1 V=1 DESTDIR="/" libdir="/usr/lib/" bindir="/usr/bin/" mandir="/usr/share/man/" includedir="/usr/include/" install &&
install -D -m0755 "src/test/tester" "/usr/bin/efivar-tester"
