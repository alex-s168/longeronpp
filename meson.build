project('longeronpp', 'cpp',
  default_options: ['cpp_std=c++17'],
  version: '0.1.0')

# headers = [
#   'src/longeron/containers/bit_iterator.hpp',
#   'src/longeron/containers/bit_view.hpp',
#   'src/longeron/containers/hierarchical_bitset.hpp',
#   'src/longeron/containers/intarray_multimap.hpp',
#   'src/longeron/containers/iterator_pair.hpp',
#   'src/longeron/id_management/bitview_id_set.hpp',
#   'src/longeron/id_management/bitview_registry.hpp',
#   'src/longeron/id_management/cast_iterator.hpp',
#   'src/longeron/id_management/id_set_stl.hpp',
#   'src/longeron/id_management/keyed_vec_stl.hpp',
#   'src/longeron/id_management/null.hpp',
#   'src/longeron/id_management/owner.hpp',
#   'src/longeron/id_management/refcount.hpp',
#   'src/longeron/id_management/registry_stl.hpp',
#   'src/longeron/id_management/unique_registry.hpp',
#   'src/longeron/utility/asserts.hpp',
#   'src/longeron/utility/bitmath.hpp',
#   'src/longeron/utility/enum_traits.hpp',
# ]

longeronpp_dep = declare_dependency(
  include_directories: './src/'
)

if not meson.is_subproject()
  gtest_dep = dependency('gtest')
  gtest_main_dep = dependency('gtest_main')

  subdir('./examples/circuits/')

  test('hierarchical_bitset', 
    executable('hierarchical_bitset',
      ['test/hierarchical_bitset.cpp'],
      dependencies: [longeronpp_dep, gtest_dep, gtest_main_dep]),
    protocol: 'gtest')

  test('intarray_multimap', 
    executable('intarray_multimap',
      ['test/intarray_multimap.cpp'],
      dependencies: [longeronpp_dep, gtest_dep, gtest_main_dep]),
    protocol: 'gtest')

  test('bit_view', 
    executable('bit_view',
      ['test/bit_view.cpp'],
      dependencies: [longeronpp_dep, gtest_dep, gtest_main_dep]),
    protocol: 'gtest')

  test('id_registry', 
    executable('id_registry',
      ['test/id_management/registry.cpp'],
      dependencies: [longeronpp_dep, gtest_dep, gtest_main_dep]),
    protocol: 'gtest')

  test('id_set', 
    executable('id_set',
      ['test/id_management/id_set.cpp'],
      dependencies: [longeronpp_dep, gtest_dep, gtest_main_dep]),
    protocol: 'gtest')
endif
