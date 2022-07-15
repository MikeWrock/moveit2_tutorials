add_executable(collision_scene_example
    src/collision_scene_example.cpp)
target_include_directories(collision_scene_example
    PUBLIC include)
ament_target_dependencies(collision_scene_example
    ${THIS_PACKAGE_INCLUDE_DEPENDS} Boost)

install(TARGETS collision_scene_example
    ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib
<<<<<<< HEAD
        RUNTIME DESTINATION lib/${PROJECT_NAME})
=======
        RUNTIME DESTINATION lib/${PROJECT_NAME})
>>>>>>> 8f3e03235 (Tutorial dockerfiles (#463))
