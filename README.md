# test

Domain-ID can be set to 69 (somewhat between 0 and 101) with:

    export ROS_DOMAIN_ID=69

With that done, the localhost variable can be activated:

    export ROS_LOCALHOST_ONLY=1








# Steps to follow after changing the packages

### cpp-code:

In package.xml add:

    <depend>${the_packages_dependency}</depend>

In CMakeLists.txt add: 

    add_executable(${executable_name} ${directory to the executable script, like: src/add_two_ints_server.cpp})
    ament_target_dependencies(${executable_name} ${first_dependency} ${second_dependency})

## From here on you gotta be in the root directory

Check for missing dependencies:

    rosdep install -i --from-path src --rosdistro humble -y


Build the package:

    colcon build

Source the environment:

    . install/setup.bash

    
