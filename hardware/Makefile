PROJECT=rc2014compat-pico-vga
DATE=$(shell date +%Y-%m-%d-%H-%M)

all: gerber fab

gerber : $(PROJECT).kicad_pcb Makefile
	rm -rf gerber
	kikit export gerber $(PROJECT).kicad_pcb gerber
	zip -r $(PROJECT)-$(DATE)-gerber.zip gerber/

fab : $(PROJECT).kicad_pcb $(PROJECT).kicad_sch Makefile
	kikit fab jlcpcb --assembly --schematic $(PROJECT).kicad_sch --no-drc --missingError $(PROJECT).kicad_pcb fab
