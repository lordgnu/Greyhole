ARCH=i386

deb: build
	rm initd_script.sh
	rm greyhole
	rm greyhole-dfree
	rm greyhole-config-update
	rm logrotate.greyhole
	rm schema-mysql.sql
	rm schema-sqlite.sql
	rm db_migration-sqlite2mysql.sh
	rm greyhole.example.conf
	rm greyhole.cron.d
	rm greyhole.cron.weekly
	rm greyhole.cron.daily
	rm upstart.conf
	rm UPGRADING
	rm CHANGES
	rm COPYING
	rm INSTALL
	rm USAGE
	rm -rf samba-module/ docs/
	
build:
	mkdir -p $(DESTDIR)etc/init.d/
	mkdir -p $(DESTDIR)etc/init/
	mkdir -p $(DESTDIR)usr/bin/
	mkdir -p $(DESTDIR)usr/share/greyhole/
	mkdir -p $(DESTDIR)etc/logrotate.d/
	mkdir -p $(DESTDIR)usr/share/greyhole/
	mkdir -p $(DESTDIR)etc/cron.d/
	mkdir -p $(DESTDIR)etc/cron.daily/
	mkdir -p $(DESTDIR)etc/cron.weekly/
	mkdir -p $(DESTDIR)usr/share/man/man1/
	mkdir -p $(DESTDIR)usr/share/man/man5/

	install -m 0755 -D -p initd_script.sh $(DESTDIR)etc/init.d/greyhole
	install -m 0644 -D -p upstart.conf $(DESTDIR)etc/init/greyhole.conf
	install -m 0755 -D -p greyhole $(DESTDIR)usr/bin
	install -m 0755 -D -p greyhole-dfree $(DESTDIR)usr/bin
	install -m 0755 -D -p greyhole-config-update $(DESTDIR)usr/bin
	install -m 0644 -D -p logrotate.greyhole $(DESTDIR)etc/logrotate.d/greyhole
	install -m 0644 -D -p schema-mysql.sql $(DESTDIR)usr/share/greyhole/
	install -m 0644 -D -p schema-sqlite.sql $(DESTDIR)usr/share/greyhole/
	install -m 0755 -D -p db_migration-sqlite2mysql.sh $(DESTDIR)usr/share/greyhole/
	install -m 0644 -D -p greyhole.example.conf $(DESTDIR)etc/greyhole.conf
	install -m 0644 -D -p greyhole.cron.d $(DESTDIR)etc/cron.d/greyhole
	install -m 0755 -D -p greyhole.cron.weekly $(DESTDIR)etc/cron.weekly/greyhole
	install -m 0755 -D -p greyhole.cron.daily $(DESTDIR)etc/cron.daily/greyhole
	
	install -m 0644 -D -p CHANGES $(DESTDIR)usr/share/greyhole/
	install -m 0644 -D -p USAGE $(DESTDIR)usr/share/greyhole/
	
	install -m 0644 -D -p docs/greyhole.1.gz $(DESTDIR)usr/share/man/man1/
	install -m 0644 -D -p docs/greyhole-dfree.1.gz $(DESTDIR)usr/share/man/man1/
	install -m 0644 -D -p docs/greyhole.conf.5.gz $(DESTDIR)usr/share/man/man5/
	
ifeq ($(ARCH), amd64)
		mkdir -p $(DESTDIR)usr/lib64/samba/vfs/
		mkdir -p $(DESTDIR)usr/lib64/greyhole/
		install -m 0644 -D -p samba-module/bin/3.4/greyhole-x86_64.so $(DESTDIR)usr/lib64/greyhole/greyhole-samba34.so
		install -m 0644 -D -p samba-module/bin/3.5/greyhole-x86_64.so $(DESTDIR)usr/lib64/greyhole/greyhole-samba35.so
		install -m 0644 -D -p samba-module/bin/3.6/greyhole-x86_64.so $(DESTDIR)usr/lib64/greyhole/greyhole-samba36.so
else
		mkdir -p $(DESTDIR)usr/lib/samba/vfs/
		mkdir -p $(DESTDIR)usr/lib/greyhole/
		install -m 0644 -D -p samba-module/bin/3.4/greyhole-i386.so $(DESTDIR)usr/lib/greyhole/greyhole-samba34.so
		install -m 0644 -D -p samba-module/bin/3.5/greyhole-i386.so $(DESTDIR)usr/lib/greyhole/greyhole-samba35.so
		install -m 0644 -D -p samba-module/bin/3.6/greyhole-i386.so $(DESTDIR)usr/lib/greyhole/greyhole-samba36.so
endif
