#-----------------------------------------------------------------------------
#
#  CMake Config
#
#  Osmium Tool Tests - show
#
#-----------------------------------------------------------------------------

function(check_show _name _input _output _options)
    check_output(show ${_name} "show --no-pager ${_options} show/${_input}" "show/${_output}")
endfunction()


#-----------------------------------------------------------------------------

check_show(debug input.osm output-debug.txt "-d")
check_show(opl input.osm output-opl.opl "-o")
check_show(xml input.osm output-xml.osm "-x")


#-----------------------------------------------------------------------------