
CC=gcc

#CFLAGS=-c -g -I /usr/include/mysql
#LDFLAGS=-g

CXXFLAGS = -O2 -I.. -march=native
CFLAGS= $(CXXFLAGS) -std=gnu99
LDFLAGS=-O2 -lgmp

SOURCES=lyra2re.c lyra2v2.c Lyra2.c lyra2z.c Lyra2-z.c Sponge.c allium.c SWIFFTX/SWIFFTX.c \
	c11.c x11.c x12.c x13.c hsr14.c x14.c x15.c x17.c x18.c \
	blake.c blakecoin.c blake2s.c jha.c keccak.c lbry.c tribus.c \
	deep.c fresh.c groestl.c neoscrypt.c nist5.c quark.c qubit.c skein.c skein2.c \
	bitcore.c timetravel.c x11evo.c x16r.c x16s.c xevan.c bastion.c hmq17.c sonoa.c \
	bmw.c luffa.c pentablake.c vitalium.c whirlpool.c whirlpoolx.c zr5.c \
	scrypt.c scryptn.c sha256.c sha256t.c \
	yescrypt.c yescrypt-opt.c sha256_Y.c \
	yespower.c yespower-opt.c sha256-P.c \
	a5a.c a5amath.c m7m.c magimath.cpp velvet.c \
	argon2a.c blake2/blake2b.c ar2/argon2.c ar2/core.c ar2/encoding.c ar2/opt.c ar2/thread.c ar2/ar2-scrypt-jane.c \
	hive.c pomelo.c hex.c argon2d.c geek.c balloon.c bcd.c \
	phi.c phi2.c polytimos.c rainforest.c renesis.c skunk.c sib.c veltor.c gost.c aergo.c x22i.c x21s.c lbk3.c pipehash.c dedal.c \
	binarium_hash_v1.c binarium_hash_v1/hashing/streebog/table/stribog.c binarium_hash_v1/hashing/whirlpool/whirlpool.c binarium_hash_v1/hashing/whirlpool/byte_order.c binarium_hash_v1/encryption/gost2015_kuznechik/SIMD.c binarium_hash_v1/encryption/gost2015_kuznechik/SIMD_tables.c binarium_hash_v1/encryption/gost2015_kuznechik/shared/tables.c binarium_hash_v1/encryption/three_fish/libskein_skein.cc binarium_hash_v1/encryption/salsa20/salsa20.c 

OBJECTS=$(SOURCES:%.c=%.o) $(SOURCES:%.cpp=%.o) $(SOURCES:%.cc=%.o)
OUTPUT=libalgos.a

all: $(SOURCES) $(OUTPUT)

$(OUTPUT): $(OBJECTS)
	ar rc $@ $(OBJECTS)
	touch ../stratum.cpp

.cpp.o:
	$(CC) $(CXXFLAGS) -c $< -o $@

.c.o:
	$(CC) $(CFLAGS) -c $< -o $@

#	$(CC) $(CFLAGS) -std=gnu99 -Wno-pointer-sign -Wno-pointer-to-int-cast -funroll-loops -fvariable-expansion-in-unroller -fmerge-all-constants -fbranch-target-load-optimize2 -fsched2-use-superblocks -falign-loops=16 -falign-functions=16 -falign-jumps=16 -falign-labels=16 -Ofast -flto -fuse-linker-plugin -ftree-loop-if-convert-stores -DUSE_ASM -pg $<

clean:
	rm -f *.o
	rm -f ar2/*.o
	rm -f blake2/*.o	
