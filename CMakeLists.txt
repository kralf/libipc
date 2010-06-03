cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libipc
  VERSION 3.8.4
  RELEASE stable
  SUMMARY "IPC provides flexible, efficient message passing between processes."
  AUTHOR "Reid Simmons"
  CONTACT "reids@cs.cmu.edu"
  HOME "http://www.cs.cmu.edu/~ipc"
  LICENSE "Simplified BSD License"
  PREFIX ipc-
  INSTALL /usr
)

remake_add_directories(doc)

remake_pack_deb()
remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "development headers"
  libipc
)
remake_pack_deb(
  ARCH all
  COMPONENT doc
  DESCRIPTION "documentation"
)
