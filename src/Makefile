.PHONY: clean 
all: game

CLASS_IMP = Actor.cpp                                                          \
            Asteroid.cpp                                                       \
            CircleComponent.cpp                                                \
            Component.cpp                                                      \
            Game.cpp                                                           \
            InputComponent.cpp                                                 \
            Laser.cpp                                                          \
            Math.cpp                                                           \
            MoveComponent.cpp                                                  \
            Random.cpp                                                         \
            Shader.cpp                                                         \
            Ship.cpp                                                           \
            SpriteComponent.cpp                                                \
            Texture.cpp                                                        \
            VertexArray.cpp                                                    \

CLASS_HEADERS = $(CLASS_IMP:.cpp=.h)

clean: 
	rm -f ./game

game: $(CLASS_HEADERS) $(CLASS_IMP) Main.cpp
	g++ $(CLASS_IMP) Main.cpp \
        `sdl2-config --libs --cflags` -lSDL2_image -lSOIL -lGLEW -lGL -o game


%.html: %.md 
	pandoc -s $< -o $@
