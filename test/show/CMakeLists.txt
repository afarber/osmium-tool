#-----------------------------------------------------------------------------
#
#  CMake Config
#
#  Osmium Tool Tests - show
#
#-----------------------------------------------------------------------------

function(check_show _name _input _output _options)
    check_output(show ${_name} "show ${_options} show/${_input}" "show/${_output}")
endfunction()


#-----------------------------------------------------------------------------

# Windows includes ANSI color codes in debug output, while Unix systems may filter them through pager
if(WIN32)
    check_show(debug input.osm output-debug-windows.txt "-f debug")
else()
    check_show(debug input.osm output-debug.txt "-f debug")
endif()
check_show(opl input.osm output-opl.opl "-f opl")
check_show(xml input.osm output-xml.osm "-f xml")


#-----------------------------------------------------------------------------