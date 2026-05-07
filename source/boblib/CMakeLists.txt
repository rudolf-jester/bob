# -----------------------------------------------------------------------------
# Define Include Directories

set(INC
	# Internal Include Directories
	PUBLIC .
	
	# External Include Directories
	
)

# -----------------------------------------------------------------------------
# Define System Include Directories

set(INC_SYS
	# External System Include Directories
	
)

# -----------------------------------------------------------------------------
# Define Source Files

set(SRC
	LIB_assert.h
	LIB_listbase.h
	LIB_utildefines.h
	LIB_utildefines_variadic.h
	
	intern/assert.c
	intern/listbase.c
)

# -----------------------------------------------------------------------------
# Define Library Dependencies

set(LIB
	# Internal Library Dependencies
	bob::intern::guardedalloc
	bob::intern::atomic
	
	# External Library Dependencies
	
)

# -----------------------------------------------------------------------------
# Declare Library

bob_add_lib(boblib "${SRC}" "${INC}" "${INC_SYS}" "${LIB}")
add_library(bob::source::boblib ALIAS boblib)

# -----------------------------------------------------------------------------
# Define Include Directories (Test)

set(INC
	# Internal Include Directories
	PUBLIC .
	
	# External Include Directories
	
)

# -----------------------------------------------------------------------------
# Define System Include Directories (Test)

set(INC_SYS
	# External System Include Directories
	
)

# -----------------------------------------------------------------------------
# Define Source Files (Test)

set(TEST
	test/listbase.cc
)

# -----------------------------------------------------------------------------
# Define Library Dependencies (Test)

set(LIB
	# Internal Library Dependencies
	bob::intern::guardedalloc
	bob::source::boblib
	
	# External Library Dependencies
	${PTHREADS_LIBRARIES}
	
)

# -----------------------------------------------------------------------------
# Declare Test

bob_add_test_executable(boblib "${TEST}" "${INC}" "${INC_SYS}" "${LIB}")
