project (mpir-generic C)

cmake_minimum_required (VERSION 2.8.6)

include_directories("./")
include_directories("./fft")
include_directories("./mpf")
include_directories("./mpq")
include_directories("./mpn/generic")
include_directories("./mpz")
include_directories("./printf")
include_directories("./scanf")

file(
	GLOB mpir_SRC
	"./*.h"
	"./*.c"
	"./fft/*.c"
	"./mpf/*.c"
	"./mpn/generic/*.c"
	"./mpq/*.c"
	"./mpz/*.c"
	"./printf/*.c"
	"./scanf/*.c"
)

add_definitions(-DHAVE_CONFIG_H)
add_definitions(-D_LIB)
add_definitions(-D_WIN64) #usually building for x64

add_library(mpir ${mpir_SRC})

