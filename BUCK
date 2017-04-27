macos_sources = glob([
  'lib/source/gainput/**/*.mm',
])

macos_exported_linker_flags = [
  '-framework', 'Foundation',
  '-framework', 'CoreFoundation',
  '-framework', 'Cocoa',
  '-framework', 'AppKit',
  '-framework', 'IOKit',
]

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
    ('^macos.*', macos_sources),
  ],
  compiler_flags = [
    '-DGAINPUT_LIB_DYNAMIC',
  ],
  exported_platform_linker_flags = [
    ('^macos.*', macos_exported_linker_flags),
  ],
  visibility = [
    'PUBLIC',
  ],
)
