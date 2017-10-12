set(SRC_sz
		include/CompressElement.h include/DynamicDoubleArray.h include/rw.h include/conf.h include/dataCompression.h
                include/DynamicFloatArray.h include/VarSet.h include/sz.h include/Huffman.h include/ByteToolkit.h include/szf.h
		include/sz_float.h include/sz_double.h include/callZlib.h include/TypeManager.h
		include/sz_int8.h include/sz_int16.h include/sz_int32.h include/sz_int64.h include/szd_int8.h include/szd_int16.h include/szd_int32.h include/szd_int64.h
		include/sz_float_pwr.h include/sz_double_pwr.h include/szd_float.h include/szd_double.h include/szd_float_pwr.h include/szd_double_pwr.h
		include/DynamicByteArray.h include/DynamicIntArray.h include/TightDataPointStorageI.h include/TightDataPointStorageD.h include/TightDataPointStorageF.h
		src/ByteToolkit.c src/dataCompression.c src/DynamicIntArray.c src/szf.c
                src/CompressElement.c src/DynamicByteArray.c src/rw.c
                src/TightDataPointStorageI.c src/TightDataPointStorageD.c src/TightDataPointStorageF.c
                src/conf.c src/DynamicDoubleArray.c src/rwf.c src/TypeManager.c
                src/DynamicFloatArray.c src/VarSet.c src/callZlib.c src/Huffman.c
                src/sz_float.c src/sz_double.c src/sz_int8.c src/sz_int16.c src/sz_int32.c src/sz_int64.c
                src/szd_float.c src/szd_double.c src/szd_int8.c src/szd_int16.c src/szd_int32.c src/szd_int64.c src/sz.c
                src/sz_float_pwr.c src/sz_double_pwr.c src/szd_float_pwr.c src/szd_double_pwr.c )

append_property(SOURCE ${SRC_sz}
    PROPERTY COMPILE_FLAGS "-fPIC")

add_library(sz OBJECT ${SRC_sz})
target_include_directories(sz PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/include" "${CMAKE_CURRENT_SOURCE_DIR}/../zlib")
