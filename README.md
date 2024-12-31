# libcurl for Android (x86_64)

This is a customized build of libcurl for Android x86_64 platform, with OpenSSL support.

## Build Configuration

- Target Platform: Android (x86_64)
- SSL/TLS: OpenSSL v3+
- Build Type: Static Library
- Compiler: Clang 14
- Android API Level: 31+

## Dependencies

- Android NDK r23b
- OpenSSL v3+ (built for Android)
- Clang 14

## Build Instructions

1. Set environment variables:

export OPENSSL_DIR=/path/to/openssl
export CPPFLAGS="-I${OPENSSL_DIR}/include"
export LDFLAGS="-L${OPENSSL_DIR}"
export LIBS="-lssl -lcrypto -lc++"

2. Configure and build:

/configure \
--host=x86_64-linux-android \
--with-pic \
--disable-shared \
--with-openssl="${OPENSSL_DIR}" \
--with-ssl="${OPENSSL_DIR}" \
--without-libpsl
make -j$(nproc)

# License

[curl license](https://curl.se/docs/copyright.html)

## Original Project

This is a fork of [curl/curl](https://github.com/curl/curl) customized for Android builds.







