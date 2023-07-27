# AC_INIT(systemd-glib, 1.0)
project('systemd-glib', 'vala', 'c', version: '1.0')


glib_dep  = dependency('glib-2.0')
go_ob_dep = dependency('gobject-2.0')
gio_dep   = dependency('gio-unix-2.0')

dependencies = [
  glib_dep,
  go_ob_dep,
  gio_dep
]

# AC_CONFIG_HEADERS([config.h])
conf = configuration_data()
conf.set_quoted('VERSION', meson.project_version())
configure_file(output: 'config.h', configuration: conf)

subdir('src')
# AC_OUTPUT([
# Makefile
# src/systemd-glib.pc
# src/Makefile
# ])

