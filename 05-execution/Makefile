
# ------------------------------- each command on newShell ? ------------
newshell: 
	cd ..
	echo `pwd` # no affect of the previous cd 
	cd ..;echo `pwd` # affects, as in same line

	-false

	# Same as above
	cd ..; \
	echo `pwd`

# ------------------------------- recursive use of make ------------
new_contents = "hello:\n\ttouch inside_file"
recursive:
	mkdir -p subdir
	printf $(new_contents) | sed -e 's/^ //' > subdir/makefile
	cd subdir && $(MAKE) 



# ------------------------------- Error handling ------------
# make -k (means keep-going)
# make -i (means ignore-errors)
# use a hyphen (-) before a command to suppress the error

# the default shell is `/bin/sh`, to change it, use SHELL=/bin/bash
# run `make -s` or use @ before each of the echo command to stop it from being printed







# ------------------------------- export ------------
# .EXPORT_ALL_VARIABLES:  
# Uncomment the above line , if you want to export all the variables


new_contents = "hello:\n\\t@echo \$$(cooly)"

all:
	mkdir -p subdir
	echo $(new_contents) | sed -e 's/^ //' > subdir/makefile
	@echo "---MAKEFILE CONTENTS---"
	@cd subdir && cat makefile
	@echo "---END MAKEFILE CONTENTS---"
	cd subdir && $(MAKE)

# Note that variables and exports. They are set/affected globally.
cooly = "Hi from subdicectory!"
export cooly
# This would nullify the line above: unexport cooly

export chk="for checking purpose"

clean:
	rm -rf subdir



# checkout dry-run, touch, old-file options from https://www.gnu.org/software/make/manual/make.html#Options-Summary