# AFL-Fuzzing

american fuzzy lop (afl) does instrumented fuzzing and is probably the best fuzzing tool available at the moment.
since it is a compile time instrumented fuzzing which adds instruction to an applications code to enable the fuzzer to detect code path in th the application.
it then uses a promissing to fuzzing samples that expose large parts of the code for further fuzzing.
When installed it will provide you wrappers for gcc that add the instrumentation code
When everything is done correct you should see new paths every now and then. 
If total paths stays at 1 you probably have set up something wrong.
The most interesting value is the uniq crashes. There you will see if you found any segfaults, most of them will likely be memory access errors.
The samples that create crashes will be collected in out/crashes.
You will also find potential hangs in out/hangs, however you should check if they really hang your tool. 
The default timeout of afl is quite low so you'll see a lot of false positives here.
american fuzzy lop does a lot of file writes (hundreds or thousands per second)
