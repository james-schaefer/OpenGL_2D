##---------------------------------------------------------------------
## BUILD libdearimgui
##---------------------------------------------------------------------
.PHONY: clean

IMGUI_SOURCES  = ./imgui_impl_sdl.cpp 
IMGUI_SOURCES += ./imgui_impl_opengl3.cpp
IMGUI_SOURCES += ./imgui.cpp 
IMGUI_SOURCES += ./imgui_demo.cpp
IMGUI_SOURCES += ./imgui_draw.cpp 
IMGUI_SOURCES += ./imgui_widgets.cpp
IMGUI_SOURCES += ./libs/gl3w/GL/gl3w.c

IMGUI_OBJS = $(addsuffix .o, $(basename $(notdir $(IMGUI_SOURCES))))

CFLAGS = -I. -I./libs/gl3w -DIMGUI_IMPL_OPENGL_LOADER_GL3W
CFLAGS += -g -Wall -Wformat 

CXXFLAGS = $(CFLAGS) 
CXXFLAGS += -std=c++17
CXXFLAGS += `sdl2-config --cflags`
LIBS += -lGL -ldl `sdl2-config --libs`

%.o:%.cpp
	$(CXX) $(CXXFLAGS) -c -o $@ $<

%.o:./libs/gl3w/GL/%.c
	$(CC) $(CFLAGS) -c -o $@ $<

%.o:./libs/glad/src/%.c
	$(CC) $(CFLAGS) -c -o $@ $<

libdearimgui.a: $(IMGUI_OBJS) 
	ar -cq libdearimgui.a $(IMGUI_OBJS) 

clean: 
	rm -f $(IMGUI_OBJS)
	rm -f libdearimgui.a
