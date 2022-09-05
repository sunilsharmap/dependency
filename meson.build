project('dependency', ['c'],
  default_options: ['werror=true', 'buildtype=debugoptimized'],
  version: '0.0.1',
)

cc = meson.get_compiler('c')
compiler_id = cc.get_id()

args = []
if get_option('default_library') == 'shared' and compiler_id == 'msvc'
  args = ['-DBUILD_SHARED_LIB']
endif

incs = include_directories('include')

srcs = files(
  'src/dependency.c',
)

libdependency = library('dependency', srcs,
  include_directories: incs,
  c_args: args,
  install: true,
  soversion: '',
  version: meson.project_version(),
)

libdependency_dep = declare_dependency(
  include_directories: incs,
  link_with: libdependency,
)
