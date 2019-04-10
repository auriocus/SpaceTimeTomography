CFLAGS= -I Math/ -I ImageFormationModel/ -I ST_Tomo/ -I ThirdParty/include/ -I ThirdParty/gmm-4.2/include/ -std=c++11 -I/usr/local/include/eigen3/ -Dcimg_display=0
LDFLAGS=-framework GLUT -ltiff -framework OpenGL `pkg-config --libs argtable2` -lGLEW

VPATH=ST_Tomo/ ImageFormationModel/ Math/
CPPS:=main.cpp $(wildcard ST_Tomo/*.cpp)
CPPS:=$(CPPS) $(wildcard ImageFormationModel/*.cpp)
CPPS:=$(CPPS) $(wildcard Math/*.cpp)
OBJS:=$(patsubst %.cpp,%.o,$(CPPS))

EXE=SpaceTime

all: $(EXE)

clean:
	rm -f $(OBJS)

%.o: %.cpp
	g++ $(CFLAGS) -c $< -o $@

$(EXE): $(OBJS)
	g++ $(OBJS) $(LDFLAGS) -o $@
