patch -p1 < /var/spool/lunar/gtkmm-2.24.4-missing-includes.patch &&

patch -p1 < /var/spool/lunar/gtkmm-2.24.4-newer-glibmm.patch &&

patch -p1 < /var/spool/lunar/gtkmm-2.24.4-papersize.patch &&

./configure  --prefix=${GNOME210_PREFIX:-/usr} \
             --build=$BUILD       \
             --sysconfdir=/etc    \
             --localstatedir=/var \
             --infodir=${GNOME210_PREFIX:-/usr}/share/info \
             --mandir=${GNOME210_PREFIX:-/usr}/share/man   \
             $OPTS                                        &&

default_make
