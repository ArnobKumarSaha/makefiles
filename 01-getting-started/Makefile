# ------------------------------------------- 1 Basic syntax
#target: prerequisites
#<TAB> recipe

# ------------------------------------------- 2 Default shell
# as /bin/sh is the default shell for makefiles , override the SHELL variable to use bash
SHELL := /bin/bash






# ------------------------------------------- 3 .PHONY
date:
	date

# `make date` will print out the date
# but if you first create a file named 'date' in the current directory,
# `make date` will print 'make: 'date' is up to date.'
# so, If you have a file named as the target already in your filesystem, then make target doesn’t work.
# use `.PHONY: <target-name>` before the target-declaration to avoid such situations.






# ------------------------------------------- 4 .DEFAULT_GOAL
ifeq ($(.DEFAULT_GOAL),)
  $(warning no default goal is set)
endif

.PHONY: foo
foo: ; @echo $@

$(warning default goal is $(.DEFAULT_GOAL)) # 'date' is still the default_goal
# not foo, as .default_goal was filled, & it was not reassinged or resetted.

# Reset the default goal.
.DEFAULT_GOAL :=
# it is reseted now. The first target is the DEFAULT_GOAL if nothing is specified.

.PHONY: bar
bar: ; @echo $@ 

$(warning default goal is $(.DEFAULT_GOAL)) # 'bar' is the default_goal now
# directly assinging
.DEFAULT_GOAL := foo







# ------------------------------------------- 5 General example
.PHONY: all say_hello generate clean
all: say_hello generate

say_hello:
	@echo "Hello world"

generate:
	@echo "Creating empty text files..."
	touch file-{1..10}.txt

clean:
	@echo "Cleaning up..."
	rm *.txt

# if we just run 'make', the default goal will be executed
# In our case, the last value of default_goal is 'foo', so targer foo will be run.







# ------------------------------------------- 6 :different types of assingment
XX := $(shell date) # := is the simple assingment, date will be executed 
YY = $(shell date)  # = is the recursive assingment, date will executed each time you use YY 
tt:
	@echo $(XX)
	@echo $(YY)
	$(shell sleep 2)
	@echo $(XX) # this is same as previous 
	@echo $(YY) # but this one changes

# ?= Conditional assignment assigns a value to a variable only if it does not have a value