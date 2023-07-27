sources = [
  'systemd-automount-iface.vala',
  'systemd-device-iface.vala',
  'systemd-job-iface.vala',
  'systemd-manager-iface.vala',
  'systemd-mount-iface.vala',
  'systemd-path-iface.vala',
  'systemd-scope-iface.vala',
  'systemd-service-iface.vala',
  'systemd-slice-iface.vala',
  'systemd-snapshot-iface.vala',
  'systemd-socket-iface.vala',
  'systemd-swap-iface.vala',
  'systemd-target-iface.vala',
  'systemd-timer-iface.vala',
  'systemd-unit-iface.vala',
]

systemd_glib_lib = shared_library('systemd-glib',
                     sources,
                     vala_header: 'systemd-glib.h',
                     vala_vapi: 'systemd-glib.vapi',
                     vala_gir: 'Systemd-1.0.gir',
                     dependencies : dependencies,
                     install: true,
                     install_dir: [true, true, true, true])

g_ir_compiler = find_program('g-ir-compiler')
typelib = custom_target(meson.project_name() + '-typelib',
                        command: [g_ir_compiler, '--output', '@OUTPUT@', meson.current_build_dir() / 'Systemd-1.0.gir'],
                        # input: meson.current_build_dir() + '/Systemd-1.0.gir',
                        output: 'Systemd-1.0.typelib',
                        depends: systemd_glib_lib,
                        install: true,
                        install_dir: get_option('libdir') / 'girepository-1.0')

pkg = import('pkgconfig')
pkg.generate(systemd_glib_lib,
             requires: gio_dep,
             version : '1.0',
             name : 'systemd-glib',
             filebase : 'systemd-glib',
             description : 'GDBus client library for systemd')
