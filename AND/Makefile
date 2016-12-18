GNET=gnetlist -L ../.. -g spice-noqsi
SPICE=ngspice
SCH_NAME=AND
ADDITIONAL_FILES=submicron.inc

%.net : %.sch
	$(GNET) $< -o $@

.PHONY : simulation

simulation : $(SCH_NAME).net CMOS_Inverter.net
	$(SPICE) $(SCH_NAME).net $(ADDITIONAL_FILES)

clean : 
	rm -f $(SCH_NAME).net CMOS_Inverter.net \#* *~
