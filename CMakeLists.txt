cmake_minimum_required(VERSION 3.5)
project(calculator C)

# Ajouter les sous-répertoires
add_subdirectory(include)
add_subdirectory(src)

# Inclure les répertoires d'en-tête
include_directories(include)

# Activer les tests
enable_testing()

# Ajouter les tests existants avec vérification de la sortie
add_test(NAME t1 COMMAND src/calculator add 2 3)
set_tests_properties(t1 PROPERTIES PASS_REGULAR_EXPRESSION "5.000000")

add_test(NAME t2 COMMAND src/calculator sub 3 -2)
set_tests_properties(t2 PROPERTIES PASS_REGULAR_EXPRESSION "5.000000")

add_test(NAME t3 COMMAND src/calculator mul 5 5)
set_tests_properties(t3 PROPERTIES PASS_REGULAR_EXPRESSION "25.000000")

add_test(NAME t4 COMMAND src/calculator div 1 5)
set_tests_properties(t4 PROPERTIES PASS_REGULAR_EXPRESSION "0.200000")

# Ajouter le nouveau test pour la fonction car avec vérification de la sortie
add_test(NAME t5 COMMAND src/calculator car 5)
set_tests_properties(t5 PROPERTIES PASS_REGULAR_EXPRESSION "25")
