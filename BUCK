macos_sources = glob([
  'lib/source/gainput/**/*.mm',
])

macos_exported_linker_flags = [
  '-framework', 'Foundation',
  '-framework', 'AppKit',
  '-framework', 'IOKit',
]

linux_sources = glob([])
linux_exported_linker_flags = ['-lX11']


cxx_library(
  name = 'gainput',
  header_namespace = 'gainput',
  exported_headers = subdir_glob([
    ('lib/include/gainput', '**/*.h'),
  ]),
  srcs = glob([
    'lib/source/gainput/**/*.cpp',
  ]),
  platform_srcs = [
    ('^linux.*', linux_sources),
    ('^macos.*', macos_sources),
  ],
  compiler_flags = [
    '-DGAINPUT_LIB_DYNAMIC',
  ],
  exported_platform_linker_flags = [
    ('^linux.*', linux_exported_linker_flags),
    ('^macos.*', macos_exported_linker_flags),
  ],
  visibility = [
    'PUBLIC',
  ],
)
