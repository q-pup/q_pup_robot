cmake_minimum_required(VERSION 3.0.2)
project(qpup_bringup)

find_package(catkin REQUIRED)

catkin_package()

install(DIRECTORY launch rqt
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
        )

install(PROGRAMS
        scripts/bringup_can.sh
        scripts/bringup_fake_can.sh
        scripts/bringup_jetson_can.sh
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
        )

catkin_install_python(PROGRAMS scripts/clock_server.py
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
