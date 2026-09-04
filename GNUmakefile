DISPLAY := custom
BOARD := sensorwatch_pro

PATH := $(PATH):/usr/lib/emscripten

-include Makefile

sim:
	emmake $(MAKE)

ifndef EMSCRIPTEN
build/movement.o: movement_config.h
else
build-sim/movement.o: movement_config.h
endif

serve: build-sim/firmware.html
	xdg-open "http://localhost:8000/firmware.html"
	python -m http.server -d build-sim

clean:
	$(MAKE) -f Makefile clean
	emmake $(MAKE) -f Makefile clean
