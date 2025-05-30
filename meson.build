project('hyperblock-server', 'cpp', version : '0.1.0', meson_version : '>=1.0.0')

if host_machine.system() == 'windows'
 override_args = ['cpp_std=vc++latest']
 common_cpp_args =  ['-D_WIN32_WINNT=0x0601']
else
 override_args = ['cpp_std=c++23']
 common_cpp_args = []
endif


argparse = dependency('argparse')
mmo = dependency('mmo')

dependencies = [
  argparse
]

server = executable('hyperblock-server',
  ['src/server.cpp'],
  dependencies : [argparse],
  include_directories : include_directories('src/'),
  cpp_args : common_cpp_args,
  override_options: override_args,
  install: true,
)

tools = executable('hyperblock-tools',
  ['src/tools.cpp'],
  dependencies : [argparse],
  include_directories : include_directories('src'),
  cpp_args : common_cpp_args,
  override_options: override_args,
  install: true,
)
