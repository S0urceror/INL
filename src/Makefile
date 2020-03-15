ASM = sjasmplus
ASMFLAGS = --raw=$@ --sym=$(basename $@).sym
OUTPUT_DIR = ../dist

all: $(OUTPUT_DIR)/inl.com
.PHONY: all clean copy

$(OUTPUT_DIR)/inl.com: $(OUTPUT_DIR)/inl-tran.dat $(OUTPUT_DIR)/inl-res.dat
	cat $(OUTPUT_DIR)/inl-tran.dat $(OUTPUT_DIR)/inl-res.dat > $(OUTPUT_DIR)/inl.com
	cp $(OUTPUT_DIR)/inl.com /Users/mario/Development/msx/USB/drivers/UsbEthernet/dist/
	cp $(OUTPUT_DIR)/inl-tran.sym /Users/mario/Development/msx/USB/drivers/UsbEthernet/dist/

$(OUTPUT_DIR)/inl-tran.dat: inl-tran.asm
	$(ASM) $(ASMFLAGS) $< 
	
$(OUTPUT_DIR)/inl-res.dat: inl-res.asm
	$(ASM) $(ASMFLAGS) $< 

clean:
	-rm $(OUTPUT_DIR)/*.rom
	-rm $(OUTPUT_DIR)/*.com
	-rm $(OUTPUT_DIR)/*.bin
	-rm $(OUTPUT_DIR)/*.sym
