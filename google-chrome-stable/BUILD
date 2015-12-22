message `pwd`

prepare_install  &&

message "Adding support for CHROMIUM_USER_FLAGS..."  &&
sed -i 's/ "$@"/ $CHROMIUM_USER_FLAGS "$@"/' opt/google/chrome/google-chrome  &&

message "Installing Chrome"  &&

cp -a opt/google/ /usr/lib/  &&

message "Fixing launch script..."  &&
ln -sf /usr/lib/google/chrome/google-chrome /usr/bin/google-chrome-stable  &&

message "Fixing Chrome icon resolution..."  &&
sed -i "/Exec=/i\StartupWMClass=Google-chrome-$_channel" usr/share/applications/google-chrome.desktop  &&
install -Dm644 usr/share/applications/google-chrome.desktop /usr/share/applications/google-chrome.desktop  &&

install -Dm644 usr/share/gnome-control-center/default-apps/google-chrome.xml /usr/share/gnome-control-center/default-apps/google-chrome.xml  &&

gzip usr/share/man/man1/google-chrome.1  &&
install -Dm644 usr/share/man/man1/google-chrome.1.gz /usr/share/man/man1/google-chrome.1.gz  &&

message "Installing icons"
for i in 16x16 22x22 24x24 32x32 48x48 64x64 128x128 256x256; do
    install -Dm644 /usr/lib/google/chrome/product_logo_${i/x*}.png \
                   /usr/share/icons/hicolor/$i/apps/google-chrome.png
done

