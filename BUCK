load('//:subdir_glob.bzl', 'subdir_glob')
load('//:buckaroo_macros.bzl', 'buckaroo_deps_from_package', 'buckaroo_cell')

deps = \
  buckaroo_deps_from_package('github.com/buckaroo-pm/boost-array') + \
  buckaroo_deps_from_package('github.com/buckaroo-pm/boost-container') + \
  buckaroo_deps_from_package('github.com/buckaroo-pm/boost-numeric_conversion') + \
  buckaroo_deps_from_package('github.com/buckaroo-pm/boost-range') + \
  [ buckaroo_cell('github.com/buckaroo-pm/boost-math') + '//:math-headers' ]

prebuilt_cxx_library(
  name = 'lexical-cast',
  header_only = True,
  header_namespace = 'boost',
  exported_headers = subdir_glob([
    ('include/boost', '**/*.hpp'),
  ]),
  deps = deps,
  visibility = [
    'PUBLIC',
  ],
)
