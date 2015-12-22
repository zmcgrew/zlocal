
mkdir build &&
rm -r Source/ThirdParty/gtest/ &&
rm -r Source/ThirdParty/qunit/ &&
cd build &&

cmake -DPORT=GTK -DCMAKE_BUILD_TYPE=Release -DCMAKE_SKIP_RPATH=ON \
      -DCMAKE_INSTALL_PREFIX=/usr -DLIB_INSTALL_DIR=/usr/lib \
      -DLIBEXEC_INSTALL_DIR=/usr/lib/webkit2gtk-4.0 \
      -DENABLE_GTKDOC=ON ../ &&

default_make &&

cd ../ &&
# symlink plugin folder to a location webkit looks for it
if [ ! -e "/usr/lib/browser-plugins" ]; then
   ln -sf /usr/lib/lunar/plugins /usr/lib/browser-plugins
fi
