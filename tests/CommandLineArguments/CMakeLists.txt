cmake_minimum_required(VERSION 2.8.12)

project(CommandLineArguments NONE)

include(../../UseLATEX.cmake)

add_latex_document(HelloWorld.tex)

# Use LaTeX command line arguments to change the output directory of the
# files. Note that this will mess up the file dependencies set up by
# CMake, but will provide a clear indication of whether or not the command
# line argument was added.
set(out_dir "${CMAKE_BINARY_DIR}/output-files")
file(MAKE_DIRECTORY ${out_dir})

set_target_properties(HelloWorld_dvi HelloWorld_pdf
  PROPERTIES COMPILER_FLAGS "-output-directory=${out_dir}"
  )
