# AC_INIT(systemd-glib, 1.0)
project('systemd-glib', 'vala', 'c', version: '1.0')

dependencies = [
  dependency('glib-2.0'),
  dependency('gobject-2.0'),
  dependency('gio-unix-2.0')
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

