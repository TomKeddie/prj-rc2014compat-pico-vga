PROJECT=rc2014compat-pico-vga
DATE=$(date +%Y-%m-%d-%H-%M)

all: gerber fab
	zip -r $(PROJECT)-$(DATE).zip gerber/ fab/

gerber : $(PROJECT).kicad_pcb Makefile
	rm -rf gerber
	kikit export gerber $(PROJECT).kicad_pcb gerber

fab : $(PROJECT).kicad_pcb $(PROJECT).kicad_sch Makefile
	kikit fab jlcpcb --assembly --schematic $(PROJECT).kicad_sch --no-drc --missingError $(PROJECT).kicad_pcb fab
