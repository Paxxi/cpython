cmake_minimum_required(VERSION 3.10.0)

project(python VERSION 3.8.0 LANGUAGES C CXX ASM)
enable_language(ASM_MASM)

find_package(zlib NO_MODULE)
find_package(expat 2.2.9 NO_MODULE)
find_package(openssl 1.1.1 NO_MODULE)
find_package(bzip2 NO_MODULE)
find_package(libffi NO_MODULE)
find_package(xz NO_MODULE)
find_package(sqlite3 NO_MODULE)

add_library(python
    Include/abstract.h
    Include/asdl.h
    Include/ast.h
    Include/bitset.h
    Include/boolobject.h
    Include/bytearrayobject.h
    Include/bytes_methods.h
    Include/bytesobject.h
    Include/cellobject.h
    Include/ceval.h
    Include/classobject.h
    Include/code.h
    Include/codecs.h
    Include/compile.h
    Include/complexobject.h
    Include/context.h
    Include/cpython/abstract.h
    Include/cpython/dictobject.h
    Include/cpython/fileobject.h
    Include/cpython/initconfig.h
    Include/cpython/object.h
    Include/cpython/objimpl.h
    Include/cpython/pyerrors.h
    Include/cpython/pylifecycle.h
    Include/cpython/pymem.h
    Include/cpython/pystate.h
    Include/cpython/sysmodule.h
    Include/cpython/traceback.h
    Include/cpython/tupleobject.h
    Include/cpython/unicodeobject.h
    Include/datetime.h
    Include/descrobject.h
    Include/dictobject.h
    Include/dtoa.h
    Include/dynamic_annotations.h
    Include/enumobject.h
    Include/errcode.h
    Include/eval.h
    Include/fileobject.h
    Include/fileutils.h
    Include/floatobject.h
    Include/frameobject.h
    Include/funcobject.h
    Include/genobject.h
    Include/graminit.h
    Include/grammar.h
    Include/import.h
    Include/internal/pycore_accu.h
    Include/internal/pycore_atomic.h
    Include/internal/pycore_ceval.h
    Include/internal/pycore_code.h
    Include/internal/pycore_condvar.h
    Include/internal/pycore_context.h
    Include/internal/pycore_fileutils.h
    Include/internal/pycore_getopt.h
    Include/internal/pycore_gil.h
    Include/internal/pycore_hamt.h
    Include/internal/pycore_initconfig.h
    Include/internal/pycore_object.h
    Include/internal/pycore_pathconfig.h
    Include/internal/pycore_pyerrors.h
    Include/internal/pycore_pyhash.h
    Include/internal/pycore_pylifecycle.h
    Include/internal/pycore_pymem.h
    Include/internal/pycore_pystate.h
    Include/internal/pycore_traceback.h
    Include/internal/pycore_tupleobject.h
    Include/internal/pycore_warnings.h
    Include/interpreteridobject.h
    Include/intrcheck.h
    Include/iterobject.h
    Include/listobject.h
    Include/longintrepr.h
    Include/longobject.h
    Include/marshal.h
    Include/memoryobject.h
    Include/methodobject.h
    Include/modsupport.h
    Include/moduleobject.h
    Include/namespaceobject.h
    Include/node.h
    Include/object.h
    Include/objimpl.h
    Include/odictobject.h
    Include/opcode.h
    Include/osdefs.h
    Include/osmodule.h
    Include/parsetok.h
    Include/patchlevel.h
    Include/picklebufobject.h
    Include/py_curses.h
    Include/pyarena.h
    Include/pycapsule.h
    Include/pyctype.h
    Include/pydebug.h
    Include/pyerrors.h
    Include/pyexpat.h
    Include/pyfpe.h
    Include/pyhash.h
    Include/pylifecycle.h
    Include/pymacro.h
    Include/pymath.h
    Include/pymem.h
    Include/pyport.h
    Include/pystate.h
    Include/pystrcmp.h
    Include/pystrhex.h
    Include/pystrtod.h
    Include/Python-ast.h
    Include/Python.h
    Include/pythonrun.h
    Include/pythread.h
    Include/pytime.h
    Include/rangeobject.h
    Include/setobject.h
    Include/sliceobject.h
    Include/structmember.h
    Include/structseq.h
    Include/symtable.h
    Include/sysmodule.h
    Include/token.h
    Include/traceback.h
    Include/tracemalloc.h
    Include/tupleobject.h
    Include/ucnhash.h
    Include/unicodeobject.h
    Include/weakrefobject.h
    Modules/_abc.c
    Modules/_bisectmodule.c
    Modules/_blake2/blake2b_impl.c
    Modules/_blake2/blake2module.c
    Modules/_blake2/blake2s_impl.c
    Modules/_codecsmodule.c
    Modules/_collectionsmodule.c
    Modules/_contextvarsmodule.c
    Modules/_csv.c
    Modules/_datetimemodule.c
    Modules/_functoolsmodule.c
    Modules/_heapqmodule.c
    Modules/_io/_iomodule.c
    Modules/_io/_iomodule.h
    Modules/_io/bufferedio.c
    Modules/_io/bytesio.c
    Modules/_io/fileio.c
    Modules/_io/iobase.c
    Modules/_io/stringio.c
    Modules/_io/textio.c
    Modules/_io/winconsoleio.c
    Modules/_json.c
    Modules/_localemodule.c
    Modules/_lsprof.c
    Modules/_math.c
    Modules/_math.h
    Modules/_opcode.c
    Modules/_operator.c
    Modules/_pickle.c
    Modules/_randommodule.c
    Modules/_sha3/sha3module.c
    Modules/_sre.c
    Modules/_stat.c
    Modules/_statisticsmodule.c
    Modules/_struct.c
    Modules/_threadmodule.c
    Modules/_tracemalloc.c
    Modules/_weakref.c
    Modules/_winapi.c
    Modules/_xxsubinterpretersmodule.c
    Modules/arraymodule.c
    Modules/atexitmodule.c
    Modules/audioop.c
    Modules/binascii.c
    Modules/cjkcodecs/_codecs_cn.c
    Modules/cjkcodecs/_codecs_hk.c
    Modules/cjkcodecs/_codecs_iso2022.c
    Modules/cjkcodecs/_codecs_jp.c
    Modules/cjkcodecs/_codecs_kr.c
    Modules/cjkcodecs/_codecs_tw.c
    Modules/cjkcodecs/alg_jisx0201.h
    Modules/cjkcodecs/cjkcodecs.h
    Modules/cjkcodecs/emu_jisx0213_2000.h
    Modules/cjkcodecs/mappings_cn.h
    Modules/cjkcodecs/mappings_hk.h
    Modules/cjkcodecs/mappings_jisx0213_pair.h
    Modules/cjkcodecs/mappings_jp.h
    Modules/cjkcodecs/mappings_kr.h
    Modules/cjkcodecs/mappings_tw.h
    Modules/cjkcodecs/multibytecodec.c
    Modules/cjkcodecs/multibytecodec.h
    Modules/cmathmodule.c
    Modules/errnomodule.c
    Modules/faulthandler.c
    Modules/gcmodule.c
    Modules/getbuildinfo.c
    Modules/hashtable.c
    Modules/hashtable.h
    Modules/itertoolsmodule.c
    Modules/main.c
    Modules/mathmodule.c
    Modules/md5module.c
    Modules/mmapmodule.c
    Modules/parsermodule.c
    Modules/posixmodule.c
    Modules/rotatingtree.c
    Modules/rotatingtree.h
    Modules/sha1module.c
    Modules/sha256module.c
    Modules/sha512module.c
    Modules/signalmodule.c
    Modules/sre_constants.h
    Modules/sre_lib.h
    Modules/sre.h
    Modules/symtablemodule.c
    Modules/timemodule.c
    Modules/xxsubtype.c
    Modules/zlibmodule.c
    Objects/abstract.c
    Objects/accu.c
    Objects/boolobject.c
    Objects/bytearrayobject.c
    Objects/bytes_methods.c
    Objects/bytesobject.c
    Objects/call.c
    Objects/capsule.c
    Objects/cellobject.c
    Objects/classobject.c
    Objects/codeobject.c
    Objects/complexobject.c
    Objects/descrobject.c
    Objects/dictobject.c
    Objects/enumobject.c
    Objects/exceptions.c
    Objects/fileobject.c
    Objects/floatobject.c
    Objects/frameobject.c
    Objects/funcobject.c
    Objects/genobject.c
    Objects/interpreteridobject.c
    Objects/iterobject.c
    Objects/listobject.c
    Objects/longobject.c
    Objects/memoryobject.c
    Objects/methodobject.c
    Objects/moduleobject.c
    Objects/namespaceobject.c
    Objects/object.c
    Objects/obmalloc.c
    Objects/odictobject.c
    Objects/picklebufobject.c
    Objects/rangeobject.c
    Objects/setobject.c
    Objects/sliceobject.c
    Objects/stringlib/count.h
    Objects/stringlib/fastsearch.h
    Objects/stringlib/find.h
    Objects/stringlib/partition.h
    Objects/stringlib/replace.h
    Objects/stringlib/split.h
    Objects/structseq.c
    Objects/tupleobject.c
    Objects/typeobject.c
    Objects/unicodectype.c
    Objects/unicodeobject.c
    Objects/unicodetype_db.h
    Objects/weakrefobject.c
    Parser/acceler.c
    Parser/grammar1.c
    Parser/listnode.c
    Parser/myreadline.c
    Parser/node.c
    Parser/parser.c
    Parser/parser.h
    Parser/parsetok.c
    Parser/token.c
    Parser/tokenizer.c
    Parser/tokenizer.h
    PC/config.c
    PC/dl_nt.c
    PC/errmap.h
    PC/getpathp.c
    PC/invalid_parameter_handler.c
    PC/msvcrtmodule.c
    PC/pyconfig.h
    PC/winreg.c
    Python/_warnings.c
    Python/asdl.c
    Python/ast_opt.c
    Python/ast_unparse.c
    Python/ast.c
    Python/bltinmodule.c
    Python/bootstrap_hash.c
    Python/ceval_gil.h
    Python/ceval.c
    Python/codecs.c
    Python/compile.c
    Python/condvar.h
    Python/context.c
    Python/dtoa.c
    Python/dynamic_annotations.c
    Python/dynload_win.c
    Python/errors.c
    Python/fileutils.c
    Python/formatter_unicode.c
    Python/frozen.c
    Python/future.c
    Python/getargs.c
    Python/getcompiler.c
    Python/getcopyright.c
    Python/getopt.c
    Python/getplatform.c
    Python/getversion.c
    Python/graminit.c
    Python/hamt.c
    Python/import.c
    Python/importdl.c
    Python/importdl.h
    Python/initconfig.c
    Python/marshal.c
    Python/modsupport.c
    Python/mysnprintf.c
    Python/mystrtoul.c
    Python/pathconfig.c
    Python/peephole.c
    Python/preconfig.c
    Python/pyarena.c
    Python/pyctype.c
    Python/pyfpe.c
    Python/pyhash.c
    Python/pylifecycle.c
    Python/pymath.c
    Python/pystate.c
    Python/pystrcmp.c
    Python/pystrhex.c
    Python/pystrtod.c
    Python/Python-ast.c
    Python/pythonrun.c
    Python/pytime.c
    Python/structmember.c
    Python/symtable.c
    Python/sysmodule.c
    Python/thread_nt.h
    Python/thread.c
    Python/traceback.c
    Python/wordcode_helpers.h
    # PC/python_nt.rc
)

target_compile_definitions(python PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    _Py_HAVE_ZLIB
)

target_include_directories(python PRIVATE
    Include/
    Include/internal
    PC/
)

target_link_libraries(python PRIVATE zlib::zlibstatic ws2_32.lib version.lib shlwapi.lib)

########################################################################
## Modules
########################################################################

macro(add_py_module)
  set(options)
  set(oneValueArgs NAME )
  set(multiValueArgs SOURCES DEFINITIONS LIBRARIES)
  cmake_parse_arguments(PY_MODULE "${options}" "${oneValueArgs}"
                        "${multiValueArgs}" ${ARGN}
  )

endmacro()

## _asyncio
add_library(_asyncio SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_asynciomodule.c
)

target_compile_definitions(_asyncio PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_asyncio PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_asyncio PROPERTIES SUFFIX ".pyd")
target_link_libraries(_asyncio PRIVATE python zlib::zlibstatic ws2_32.lib version.lib shlwapi.lib)

## _bz2
add_library(_bz2 SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_bz2module.c
)

target_compile_definitions(_bz2 PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_bz2 PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_bz2 PROPERTIES SUFFIX ".pyd")
target_link_libraries(_bz2 PRIVATE python bzip2::bzip2 ws2_32.lib version.lib shlwapi.lib)

## _ctypes
add_library(_ctypes SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/_ctypes.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/callbacks.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/callproc.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/cfield.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/ctypes_dlfcn.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/ctypes.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/malloc_closure.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ctypes/stgdict.c
)

target_compile_definitions(_ctypes PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
    FFI_BUILDING
)


target_include_directories(_ctypes PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_ctypes PROPERTIES SUFFIX ".pyd")
target_link_libraries(_ctypes PRIVATE python libffi::libffi ws2_32.lib version.lib shlwapi.lib)

## _decinaml
add_library(_decimal SHARED
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/sixstep.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/sixstep.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/transpose.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/transpose.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/typearith.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/umodarith.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/vccompat.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/basearith.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/basearith.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/bits.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/constants.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/constants.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/context.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/convolute.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/convolute.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/crt.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/crt.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/difradix2.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/difradix2.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/fnt.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/fnt.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/fourstep.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/fourstep.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/io.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/io.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/mpalloc.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/mpalloc.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/mpdecimal.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/mpdecimal.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/numbertheory.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/numbertheory.h
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/_decimal.c
${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/docstrings.h
)

target_compile_definitions(_decimal PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
    MASM
    _CRT_SECURE_NO_WARNINGS
)

if(${CMAKE_GENERATOR_PLATFORM} STREQUAL "win32")
  target_compile_definitions(_decimal PRIVATE
    CONFIG_32
    PPRO
  )
elseif(${CMAKE_GENERATOR_PLATFORM} STREQUAL "x64")
  target_compile_definitions(_decimal PRIVATE
    CONFIG_64
  )
  target_sources(_decimal PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_decimal/libmpdec/vcdiv64.asm
  )
elseif(${CMAKE_GENERATOR_PLATFORM} STREQUAL "arm")
  target_compile_definitions(_decimal PRIVATE
    CONFIG_32
    ANSI
  )
elseif(${CMAKE_GENERATOR_PLATFORM} STREQUAL "arm64")
  target_compile_definitions(_decimal PRIVATE
    CONFIG_64
    ANSI
  )
endif()

target_include_directories(_decimal PRIVATE
    Include/
    Include/internal
    PC/
    Modules/_decimal/libmpdec
)

set_target_properties(_decimal PROPERTIES SUFFIX ".pyd")
target_link_libraries(_decimal PRIVATE python ws2_32.lib version.lib shlwapi.lib)

## _elementtree
add_library(_elementtree SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_elementtree.c
)

target_compile_definitions(_elementtree PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_elementtree PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_elementtree PROPERTIES SUFFIX ".pyd")
target_link_libraries(_elementtree PRIVATE python expat::libexpat ws2_32.lib version.lib shlwapi.lib)

## _hashlib
add_library(_hashlib SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_hashopenssl.c
)

target_compile_definitions(_hashlib PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_hashlib PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_hashlib PROPERTIES SUFFIX ".pyd")
target_link_libraries(_hashlib PRIVATE python openssl::crypto ws2_32.lib version.lib shlwapi.lib)

## _lzma
add_library(_lzma SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_lzmamodule.c
)

target_compile_definitions(_lzma PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_lzma PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_lzma PROPERTIES SUFFIX ".pyd")
target_link_libraries(_lzma PRIVATE python xz::lzma ws2_32.lib version.lib shlwapi.lib)

## _multiprocessing
add_library(_multiprocessing SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_multiprocessing/multiprocessing.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_multiprocessing/multiprocessing.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_multiprocessing/semaphore.c
)

target_compile_definitions(_multiprocessing PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_multiprocessing PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_multiprocessing PROPERTIES SUFFIX ".pyd")
target_link_libraries(_multiprocessing PRIVATE python ws2_32.lib version.lib shlwapi.lib)

## _overlapped
add_library(_overlapped SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/overlapped.c
)

target_compile_definitions(_overlapped PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_overlapped PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_overlapped PROPERTIES SUFFIX ".pyd")
target_link_libraries(_overlapped PRIVATE python ws2_32.lib version.lib shlwapi.lib)

## _queue
add_library(_queue SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_queuemodule.c
)

target_compile_definitions(_queue PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_queue PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_queue PROPERTIES SUFFIX ".pyd")
target_link_libraries(_queue PRIVATE python ws2_32.lib version.lib shlwapi.lib)

## _socket
add_library(_socket SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/socketmodule.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/socketmodule.h
)

target_compile_definitions(_socket PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_socket PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_socket PROPERTIES SUFFIX ".pyd")
target_link_libraries(_socket PRIVATE python iphlpapi.lib ws2_32.lib version.lib shlwapi.lib)

## _sqlite3
add_library(_sqlite3 SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/cache.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/cache.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/connection.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/connection.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/cursor.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/cursor.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/microprotocols.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/microprotocols.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/module.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/module.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/prepare_protocol.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/prepare_protocol.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/row.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/row.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/statement.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/statement.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/util.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_sqlite/util.h
)

target_compile_definitions(_sqlite3 PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
    MODULE_NAME="sqlite3"
)

target_include_directories(_sqlite3 PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_sqlite3 PROPERTIES SUFFIX ".pyd")
target_link_libraries(_sqlite3 PRIVATE python sqlite3::sqlite3 ws2_32.lib version.lib shlwapi.lib)

## _ssl
add_library(_ssl SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/_ssl.c
)

target_compile_definitions(_ssl PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(_ssl PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(_ssl PROPERTIES SUFFIX ".pyd")
target_link_libraries(_ssl PRIVATE python openssl::ssl openssl::crypto crypt32.lib ws2_32.lib version.lib shlwapi.lib)

## select
add_library(select SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/selectmodule.c
)

target_compile_definitions(select PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(select PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(select PROPERTIES SUFFIX ".pyd")
target_link_libraries(select PRIVATE python ws2_32.lib version.lib shlwapi.lib)

## pyexpat
add_library(pyexpat SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/pyexpat.c
)

target_compile_definitions(pyexpat PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(pyexpat PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(pyexpat PROPERTIES SUFFIX ".pyd")
target_link_libraries(pyexpat PRIVATE python expat::libexpat ws2_32.lib version.lib shlwapi.lib)

## unicodedata
add_library(unicodedata SHARED
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/unicodedata.c
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/unicodedata_db.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Modules/unicodename_db.h
)

target_compile_definitions(unicodedata PRIVATE
    _USRDLL
    Py_BUILD_CORE
    Py_BUILD_CORE_BUILTIN
    Py_BUILD_CORE_MODULE
)

target_include_directories(unicodedata PRIVATE
    Include/
    Include/internal
    PC/
)

set_target_properties(unicodedata PROPERTIES SUFFIX ".pyd")
target_link_libraries(unicodedata PRIVATE python ws2_32.lib version.lib shlwapi.lib)

include(CMakePackageConfigHelpers)
write_basic_package_version_file(
  ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}-config-version.cmake
  VERSION ${PROJECT_VERSION}
  COMPATIBILITY AnyNewerVersion
)

install(TARGETS ${PROJECT_NAME} EXPORT ${PROJECT_NAME}
  RUNTIME DESTINATION bin
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
)

install(DIRECTORY
  ${CMAKE_CURRENT_SOURCE_DIR}/Include/
  DESTINATION include/python
  PATTERN internal EXCLUDE
)

install(FILES
  ${CMAKE_CURRENT_SOURCE_DIR}/PC/pyconfig.h
  DESTINATION include/python
)

install(DIRECTORY
  ${CMAKE_CURRENT_BINARY_DIR}
  DESTINATION lib/python/DLLs
  FILES_MATCHING PATTERN *.pyd
  PATTERN .vs EXCLUDE
  PATTERN amd64 EXCLUDE
  PATTERN Debug EXCLUDE
  PATTERN obj EXCLUDE
)

install(DIRECTORY
    ${CMAKE_CURRENT_SOURCE_DIR}/Lib
    DESTINATION lib/python
    PATTERN plat-* EXCLUDE
    PATTERN msilib EXCLUDE
    PATTERN lib-tk EXCLUDE
    PATTERN curses EXCLUDE
    PATTERN bsddb EXCLUDE
    PATTERN *test EXCLUDE
    PATTERN idlelib EXCLUDE
)

install(EXPORT ${PROJECT_NAME}
  FILE
  ${PROJECT_NAME}.cmake
  NAMESPACE
    ${PROJECT_NAME}::
  DESTINATION
    lib/cmake/${PROJECT_NAME}
)

install(FILES
  ${CMAKE_CURRENT_SOURCE_DIR}/cmake/${PROJECT_NAME}-config.cmake
  ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}-config-version.cmake
  DESTINATION
    lib/cmake/${PROJECT_NAME}
)

export(TARGETS ${PROJECT_NAME}
  FILE
  ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}-config.cmake
  NAMESPACE ${PROJECT_NAME}::
)