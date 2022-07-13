# ------------------------------------------- 1 Pattern rules
# consider it in two ways : 1) To define own implicit rules.  2) simpler form of static pattern rules

# Define a pattern rule that compiles every .c file into a .o file
%.o : %.c
	$(CC) -c $(CFLAGS) $(CPPFLAGS) $< -o $@

# Define a pattern rule that has no pattern in the prerequisites.
# This just creates empty .c files when needed.
%.c:
	touch $@

.DEFAULT_GOAL := hi 
hi: a.c



# ------------------------------------------- 2 Double colon rules
# all: blah

# blah::
# 	@echo "hello"

# blah::
# 	@echo "hello again"