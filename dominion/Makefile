CFLAGS = -Wall -fpic -coverage -lm

rngs.o: rngs.h rngs.c
	gcc -c rngs.c -g  $(CFLAGS)

dominion.o: dominion.h dominion.c rngs.o
	gcc -c dominion.c -g  $(CFLAGS)

playdom: dominion.o playdom.c
	gcc -o playdom playdom.c -g dominion.o rngs.o $(CFLAGS)

interface.o: interface.h interface.c
	gcc -c interface.c -g  $(CFLAGS)

player: player.c interface.o
	gcc -o player player.c -g  dominion.o rngs.o interface.o $(CFLAGS)

unittest1: unittest1.c dominion.o
	gcc -o unittest1 unittest1.c -g dominion.o rngs.o $(CFLAGS)

unittest2: unittest2.c dominion.o
	gcc -o unittest2 unittest2.c -g dominion.o rngs.o $(CFLAGS)

unittest3: unittest3.c dominion.o
	gcc -o unittest3 unittest3.c -g dominion.o rngs.o $(CFLAGS)

unittest4: unittest4.c dominion.o
	gcc -o unittest4 unittest4.c -g dominion.o rngs.o $(CFLAGS)

cardtest1: cardtest1.c dominion.o
	gcc -o cardtest1 cardtest1.c -g dominion.o rngs.o $(CFLAGS)

cardtest2: cardtest2.c dominion.o
	gcc -o cardtest2 cardtest2.c -g dominion.o rngs.o $(CFLAGS)

cardtest3: cardtest3.c dominion.o
	gcc -o cardtest3 cardtest3.c -g dominion.o rngs.o $(CFLAGS)

cardtest4: cardtest4.c dominion.o
	gcc -o cardtest4 cardtest4.c -g dominion.o rngs.o $(CFLAGS)

randomtestcard1: randomtestcard1.c dominion.o
	gcc -o randomtestcard1 randomtestcard1.c -g dominion.o rngs.o $(CFLAGS)

randomtestcard2: randomtestcard2.c dominion.o
	gcc -o randomtestcard2 randomtestcard2.c -g dominion.o rngs.o $(CFLAGS)

randomtestadventurer: randomtestadventurer.c dominion.o
	gcc -o randomtestadventurer randomtestadventurer.c -g dominion.o rngs.o $(CFLAGS)

testdominion: testdominion.c dominion.o
	gcc -o testdominion testdominion.c -g dominion.o rngs.o $(CFLAGS)

unittestresults.out: unittest1.c unittest2.c unittest3.c unittest4.c cardtest1.c cardtest2.c cardtest3.c cardtest4.c dominion.o
	./unittest1 >> unittestresults.out
	echo "GCOV AFTER TEST 1" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "TEST 2:" >> unittestresults.out
	./unittest2 >> unittestresults.out
	echo "GCOV AFTER TEST 2" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "TEST 3:" >> unittestresults.out
	./unittest3 >> unittestresults.out
	echo "GCOV AFTER TEST 3" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "TEST 4:" >> unittestresults.out
	./unittest4 >> unittestresults.out
	echo "GCOV AFTER TEST 4" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "CARD TEST 1:" >> unittestresults.out
	./cardtest1 >> unittestresults.out
	echo "GCOV AFTER CARD TEST 1" >> unittestresults.out

unittestresults.out: unittest1.c unittest2.c unittest3.c unittest4.c cardtest1.c cardtest2.c cardtest3.c cardtest4.c dominion.o
	./unittest1 >> unittestresults.out
	echo "GCOV AFTER TEST 1" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "TEST 2:" >> unittestresults.out
	./unittest2 >> unittestresults.out
	echo "GCOV AFTER TEST 2" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "TEST 3:" >> unittestresults.out
	./unittest3 >> unittestresults.out
	echo "GCOV AFTER TEST 3" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "TEST 4:" >> unittestresults.out
	./unittest4 >> unittestresults.out
	echo "GCOV AFTER TEST 4" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "CARD TEST 1:" >> unittestresults.out
	./cardtest1 >> unittestresults.out
	echo "GCOV AFTER CARD TEST 1" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "CARD TEST 2:" >> unittestresults.out
	./cardtest2 >> unittestresults.out
	echo "GCOV AFTER CARD TEST 2" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "CARD TEST 3:" >> unittestresults.out
	./cardtest3 >> unittestresults.out
	echo "GCOV AFTER CARD TEST 3" >> unittestresults.out
	gcov dominion.c >> unittestresults.out
	echo "CARD TEST 4:" >> unittestresults.out
	./cardtest4 >> unittestresults.out
	echo "GCOV AFTER CARD TEST 4" >> unittestresults.out
	gcov dominion.c >> unittestresults.out

testdominion.out: testdominion.c dominion.o
	./testdominion 42 >> testdominion.out
	echo "GCOV after testdominion"
	gcov dominion.c >> testdominion.out

all: playdom player unittest1 unittest2 unittest3 unittest4 cardtest1 cardtest2 cardtest3 cardtest4 testdominion

rdm: playdom player randomtestcard1 randomtestcard2 randomtestadventurer
	./randomtestcard1 42 > randomtestcard1.out
	gcov -f dominion.c >> randomtestcard1.out
	./randomtestcard2 42 > randomtestcard2.out
	gcov -f dominion.c >> randomtestcard2.out
	./randomtestadventurer 42 > randomtestadventurer.out
	gcov -f dominion.c >> randomtestadventurer.out



clean:
	rm -f *.o playdom.exe playdom test.exe test player unittest1 unittest2 unittest3 unittest4 cardtest1 cardtest2 cardtest3 cardtest4 player.exe testInit testInit.exe *.gcov *.gcda *.gcno *.so *.a *.dSYM
