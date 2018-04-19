# Script generated with Bloom
pkgdesc="ROS - ROS package for solving the Traveling Salesman Problem using the Lin-Kernighan heuristic."


pkgname='ros-kinetic-lkh-solver'
pkgver='0.1.1_1'
pkgrel=1
arch=('any')
license=('BSD 3-Clause'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roscpp'
)

depends=('ros-kinetic-resource-retriever'
'ros-kinetic-roscpp'
)

conflicts=()
replaces=()

_dir=lkh_solver
source=()
md5sums=()

prepare() {
    cp -R $startdir/lkh_solver $srcdir/lkh_solver
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

