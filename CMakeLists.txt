# Collect all the protobuf(nanopb) generated .c files in the directory
file(GLOB MAIN_SRCS "./*.c")

# Collect all the nanopb pb_common.c, pb_encode.c, pb_decode.c source files in the directory
file(GLOB NANOPB_SRCS "./nanopb/*.c")

# Collect all the nanopb pb_common.h, pb_encode.h, pb_decode.h and pb.h header files in the directory
file(GLOB NANOPB_HEADERS_DIR "./nanopb")

idf_component_register(
  SRCS ${MAIN_SRCS} ${NANOPB_SRCS}

  # Include the messages header files and the nanopb header files
  INCLUDE_DIRS "." ${NANOPB_HEADERS_DIR}
)
