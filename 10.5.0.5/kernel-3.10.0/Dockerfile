#
#  Build docker image of db2 express-C v10.5 FP5 (64bit)
#
# # Authors:
#   * Leo (Zhong Yu) Wu       <leow@ca.ibm.com>
#
# Copyright 2015, IBM Corporation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Specify base OS with kernel 3.10.0
# Options:
#   centos:7


FROM    centos:7

MAINTAINER Leo Wu <leow@ca.ibm.com>


###############################################################
#
#               System preparation for DB2
#
###############################################################

RUN  yum -y install wget

RUN  wget http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
RUN  rpm -ivh epel-release-7-5.noarch.rpm

# Required pacakges
RUN yum install -y vi tar initscripts \
    system-config-language \
    sudo \
    passwd \
    pam \
    pam.i686 \
    ncurses-libs.i686 \
    file \
    rsyslog \
    e2fsprogs \
    libaio \
    libaio.i686 \
    compat-libstdc++-33 \
    libstdc++-devel \
    libstdc++-devel.i686 \
    dapl-devel \
    libibverbs-devel \
    sg3_utils \
    numactl \
    numactl.i686 \
    gcc-c++ \
    kernel-devel


COPY docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

# Expose the default ports for DB2 instance
EXPOSE 50000
EXPOSE 50001
EXPOSE 50002
EXPOSE 50003
EXPOSE 50004

