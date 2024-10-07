
rz_ghidra_cutter_sources = [
  'RzGhidraDecompiler.cpp',
  'RzGhidraPlugin.cpp',
  'RzGhidraDecompiler.h',
  'RzGhidraPlugin.h',
  ]

cutter_dep = dependency('libcutter')
rz_ghidra_cutter_mod = shared_module('rz_ghidra_cutter',
  rz_ghidra_cutter_sources,
  install: true,
  install_dir: join_paths(datadir, 'rizin', 'cutter', 'plugins', 'native'),
  cpp_args: [ '-DRZ_GHIDRA_SLEIGHHOME_DEFAULT="@0@"'.format(sleighhome)],
  dependencies: rz_deps + [ ghidra_dep, cutter_dep ],
  )

cutter_ghidra_dep_cargs = ['-DRZ_GHIDRA_SLEIGHHOME_DEFAULT="@0@"'.format(sleighhome)]

cutter_ghidra_dep = declare_dependency(
  link_with: rz_ghidra_cutter_mod,
  dependencies: [ ghidra_dep ],
  include_directories: [ '.' ],
  )
