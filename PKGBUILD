# This package was created to work with icinga and not nagios.

pkgname=check_mk-icinga
name=check_mk
pkgver=1.1.12p6
pkgrel=2
pkgdesc="A new general purpose Nagios-plugin for retrieving data."
license=('GPL2')
arch=('any')
url="http://mathias-kettner.de/check_mk.html"
depends=('python2' 'icinga')
source=("http://mathias-kettner.de/download/$name-$pkgver.tar.gz")
md5sums=('5392da2f0f61aeeff801463f689b91ac')

build() {
  cd $srcdir/$name-$pkgver

  export DESTDIR=$pkgdir \
	nagiosuser='icinga' \
	wwwuser='http' \
	wwwgroup='icinga' \
	nagios_binary='/usr/bin/icinga' \
	nagios_config_file='/etc/icinga/icinga.cfg' \
	nagconfdir='/etc/icinga/objects' \
	nagios_startscript='/etc/rc.d/icinga' \
	nagpipe='/var/icinga/rw/icinga.cmd' \
	check_result_path='/var/icinga/spool/checkresults' \
	nagios_status_file='/var/icinga/status.dat' \
	check_icmp_path='/usr/share/icinga/libexec/check_icmp' \
	apache_config_dir='/etc/httpd/conf' \
	htpasswd_file='/etc/icinga/htpasswd.users' \
	nagios_auth_name='Icinga Access' \
	enable_livestatus='no'

  ./setup.sh
}
