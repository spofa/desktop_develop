.PHONY:clean all


LIB_PATH=-L../glib \
			-L../spice-common/common \
			-L../win32\
			-L/usr/local/lib/ \
			-L/usr/lib 
CFLAGS = -std=gnu99

ifeq ($(SPICE_DEBUG), y)
	CFLAGS += -g 
else
	CFLAGS += -O2
endif


INC_PATH=-I../spice-common/spice-protocol\
			-I../spice-common\
			-I../win32 \
			-I../logger

SRC=test_bmp.c ../win32/create_bmp.c
OBJS=test_bmp.o 
LIBS=-lspice_glib -lspice_without_gtk -lspice-common-client \
	  -lglib-2.0 -lgio-2.0 -lgmodule-2.0 -lgobject-2.0 -lgthread-2.0 \
	  -lusb-1.0 -lusbredirhost -lusbredirparser \
	  -lxml2 -lssl -lcelt051 -lm -ljpeg -lz -lpixman-1 -lcrypto -lpulse-mainloop-glib -lpulse -lsasl2 \
	  -lgstapp-0.10 -lgstaudio-0.10 -lgstbase-0.10 -lgstinterfaces-0.10 -lgstreamer-0.10 \
	  -lavformat -lavcodec -lswresample -lswscale -lavutil -lX11

all:test_bmp

test_bmp:$(SRC)
	$(CC) -o test_bmp $(CFLAGS) $(SRC) $(INC_PATH) $(LIB_PATH) $(LIBS)  
clean:
	rm -rf test_bmp *.o
