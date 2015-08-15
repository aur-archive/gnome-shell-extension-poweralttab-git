# Maintainer: jtts
# Contributor: Christian METZLER <neroth@xeked.com> (gnome-shell-extension-weather-git was used as a template)
pkgname=gnome-shell-extension-poweralttab-git
pkgver=20130601
pkgrel=3
pkgdesc="A GNOME Shell extension that replaces predefined Alt-Tab behaviour. Iterates over available workspaces and windows."
arch=('any')
url="https://github.com/emerinohdz/PowerAltTab"
license=('GPL3')
depends=('glib2' 'gettext' 'pkg-config' 'dconf' 'gnome-shell')
makedepends=('git' 'gnome-common')
#replaces=('')
install='gschemas.install'

_gitroot="https://github.com/emerinohdz/PowerAltTab.git"
_gitname="gnome-shell-extension-poweralttab"
build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi

  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir/$_gitname"
  install -Dm644 extension.js $pkgdir/usr/share/gnome-shell/extensions/PowerAltTab@devpower.org/extension.js
  install -Dm644 metadata.json $pkgdir/usr/share/gnome-shell/extensions/PowerAltTab@devpower.org/metadata.json
  install -Dm644 README $pkgdir/usr/share/gnome-shell/extensions/PowerAltTab@devpower.org/README
}
