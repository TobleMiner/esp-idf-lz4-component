set(LIB_SRCS
  lz4/lib/lz4.c
)

idf_component_register(SRCS ${LIB_SRCS}
                       INCLUDE_DIRS lz4/lib)

# Enable if operating with larger LZ4_MEMORY_USAGE value.
# Stack usage during (de)compression is roughly 2^LZ4_MEMORY_USAGE
# Setting LZ4_HEAPMODE=1 shifts that from stack to heap
#target_compile_definitions(${COMPONENT_LIB} PUBLIC LZ4_HEAPMODE=1)
target_compile_definitions(${COMPONENT_LIB} PUBLIC LZ4_MEMORY_USAGE=10)
