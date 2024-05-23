cmake_minimum_required(VERSION 3.5)
project(calculator C)

# Inclure les répertoires d'en-tête
include_directories(include)

# Ajouter les sous-répertoires
add_subdirectory(src)

# Activer les tests
enable_testing()

# Ajouter les tests existants avec vérification de la sortie
add_test(NAME t1 COMMAND calculator add 2 3)
set_tests_properties(t1 PROPERTIES PASS_REGULAR_EXPRESSION "5.000000")

add_test(NAME t2 COMMAND calculator sub 3 -2)
set_tests_properties(t2 PROPERTIES PASS_REGULAR_EXPRESSION "5.000000")

add_test(NAME t3 COMMAND calculator mul 5 5)
set_tests_properties(t3 PROPERTIES PASS_REGULAR_EXPRESSION "25.000000")

add_test(NAME t4 COMMAND calculator div 1 5)
set_tests_properties(t4 PROPERTIES PASS_REGULAR_EXPRESSION "0.200000")

# Ajouter le nouveau test pour la fonction car avec vérification de la sortie
add_test(NAME t5 COMMAND calculator car 5)
set_tests_properties(t5 PROPERTIES PASS_REGULAR_EXPRESSION "25")
