set(srcs
    "ngtcp2/crypto/shared.c"
    "ngtcp2/crypto/wolfssl/wolfssl.c")

idf_component_register(SRCS "${srcs}"
                    INCLUDE_DIRS ngtcp2/crypto/includes
                    PRIV_INCLUDE_DIRS port/private_include ngtcp2/crypto ngtcp2/lib
                    REQUIRES ngtcp2 wolfssl)

target_compile_options(${COMPONENT_LIB} PRIVATE "-Wno-format" "-Wno-maybe-uninitialized")
target_compile_definitions(${COMPONENT_LIB} PRIVATE "-DHAVE_CONFIG_H")
