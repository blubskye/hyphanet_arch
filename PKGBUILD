# Hyphanet Arch Linux Package
# Copyright (C) 2024 blubskye
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
#
# Source: https://github.com/blubskye/hyphanet_arch

# Maintainer: blubskye <blubskye@users.noreply.github.com>

pkgname=hyphanet
pkgver=0.7.5.1503
pkgrel=1
pkgdesc="Anonymous peer-to-peer distributed data store (formerly Freenet)"
arch=('any')
url="https://www.hyphanet.org/"
license=('AGPL3')
depends=('java-runtime>=11' 'bash')
makedepends=('curl' 'jq')
backup=('etc/default/hyphanet')
install=hyphanet.install
source=(
    "hyphanet.service"
    "hyphanet.default"
    "wrapper.conf"
    "run.sh"
    "hyphanet.install"
)
sha256sums=(
    'SKIP'
    'SKIP'
    'SKIP'
    'SKIP'
    'SKIP'
)

_get_latest_build() {
    curl -s "https://api.github.com/repos/hyphanet/fred/releases/latest" | jq -r '.tag_name' | sed 's/build0*//'
}

pkgver() {
    local build=$(_get_latest_build)
    echo "0.7.5.${build}"
}

prepare() {
    local build=$(_get_latest_build)
    local build_padded=$(printf "%05d" "${build}")

    echo "Downloading Hyphanet build ${build}~ 💕"

    # Download main JAR
    curl -L -o "${srcdir}/freenet.jar" \
        "https://github.com/hyphanet/fred/releases/download/build${build_padded}/freenet-build${build_padded}.jar"

    # Get the ext JAR version from the release
    local ext_url=$(curl -s "https://api.github.com/repos/hyphanet/fred/releases/latest" | \
        jq -r '.assets[] | select(.name | startswith("freenet-ext")) | .browser_download_url')

    if [ -n "${ext_url}" ]; then
        curl -L -o "${srcdir}/freenet-ext.jar" "${ext_url}"
    else
        # Fallback to known version
        curl -L -o "${srcdir}/freenet-ext.jar" \
            "https://github.com/hyphanet/fred/releases/download/build${build_padded}/freenet-ext-29.jar"
    fi
}

package() {
    # Create directories
    install -d "${pkgdir}/opt/hyphanet"
    install -d "${pkgdir}/opt/hyphanet/lib"
    install -d -m 750 "${pkgdir}/var/lib/hyphanet"
    install -d "${pkgdir}/usr/lib/systemd/system"
    install -d "${pkgdir}/etc/default"
    install -d "${pkgdir}/usr/bin"

    # Install JAR files
    install -Dm644 "${srcdir}/freenet.jar" "${pkgdir}/opt/hyphanet/freenet.jar"
    install -Dm644 "${srcdir}/freenet-ext.jar" "${pkgdir}/opt/hyphanet/lib/freenet-ext.jar"

    # Install systemd service
    install -Dm644 "${srcdir}/hyphanet.service" "${pkgdir}/usr/lib/systemd/system/hyphanet.service"

    # Install default configuration
    install -Dm644 "${srcdir}/hyphanet.default" "${pkgdir}/etc/default/hyphanet"

    # Install wrapper config
    install -Dm644 "${srcdir}/wrapper.conf" "${pkgdir}/opt/hyphanet/wrapper.conf"

    # Install run script
    install -Dm755 "${srcdir}/run.sh" "${pkgdir}/opt/hyphanet/run.sh"

    # Create symlink
    ln -s /opt/hyphanet/run.sh "${pkgdir}/usr/bin/hyphanet"
}
