TESTS=test011 test001 test002 test003 test004 test005 test006 test007 test008 test012 test013 #exprs
TESTS+=test009 test010 test014 test015 test016 test017 test018 #if and while
TESTS+=test011 test024 test025  #functions

# test019 test020 test021 test022 test023 test024 test025 test026 
# test027 test028 test029 test030 

.PHONY: check $(TESTS) 

check: $(TESTS) 

$(TESTS): %: %.expr
#	../rc.native     $< && cat $@.input | ./$@ > $@.log && diff $@.log orig/$@.log
	cat $@.input | ../rc.native -i $< > $@.log && diff $@.log orig/$@.log
	cat $@.input | ../rc.native -s $< > $@.log && diff $@.log orig/$@.log

clean:
	rm -f test*.log *.s *~ $(TESTS)
