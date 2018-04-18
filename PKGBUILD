# Script generated with Bloom
pkgdesc="ROS - An rqt-based tool that assists monitoring tasks for <a href="http://ros.org/wiki/moveit">MoveIt!</a> motion planner developers and users. Currently the following items are monitored if they are either running, existing or published: <ul> <li>Node: /move_group</li> <li>Parameter: [/robot_description, /robot_description_semantic]</li> <li>Topic: Following types are monitored. Published &quot;names&quot; are ignored.<br/> [sensor_msgs/PointCloud, sensor_msgs/PointCloud2, sensor_msgs/Image, sensor_msgs/CameraInfo]</li> </ul> Since this package is not made by the MoveIt! development team (although with assistance from the them), please post issue reports to the designated tracker (not MoveIt!'s main tracker)."
url='http://wiki.ros.org/rqt_moveit'

pkgname='ros-kinetic-rqt-moveit'
pkgver='0.5.7_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-python-qt-binding>=0.2.19'
'ros-kinetic-rosnode'
'ros-kinetic-rospy'
'ros-kinetic-rostopic'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-py'
'ros-kinetic-rqt-py-common'
'ros-kinetic-rqt-topic'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=rqt_moveit
source=()
md5sums=()

prepare() {
    cp -R $startdir/rqt_moveit $srcdir/rqt_moveit
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

