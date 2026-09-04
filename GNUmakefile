DISPLAY := custom
BOARD := sensorwatch_pro

PATH := $(PATH):/usr/lib/emscripten

-include Makefile

build-sim/firmware.html: $(SRCS)
	emmake $(MAKE)

emulate: build-sim/firmware.html
	xdg-open "http://localhost:8000/firmware.html"
	python -m http.server -d build-sim

clean-all:
	$(MAKE) clean
	emmake $(MAKE) clean
