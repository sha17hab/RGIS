include ../common.mk
INC    = ../include
SRC    = ../src
OBJ    = ../obj
BIN    = ../bin
CPP    = $(UNIXCPP) $(UNIXCPPOPS) -I$(INC)\
         -I../../CMlib/include\
         -I../../DBlib/include\
         -I../../RGlib/include\
         -I../../UIlib/include
LINK   = $(UNIXCPP)
LIBS   = -L../../CMlib/lib\
         -L../../DBlib/lib\
         -L../../RGlib/lib\
         -L../../UIlib/lib -lUI22 -lRG22 -lDB22 -lCM10 $(UNIXLIBS)
TARGET = rgis22

INCLUDES = $(INC)/rgis.H

OBJS = $(OBJ)/RGISMain.o\
       $(OBJ)/RGISWorkspace.o\
       $(OBJ)/RGISPanels.o\
       $(OBJ)/RGISUsrFuncVec.o\
       $(OBJ)/RGISUsrFuncGrd.o\
       $(OBJ)/RGISUsrFuncNet.o\
       $(OBJ)/RGISUsrFuncQry.o\
       $(OBJ)/RGISFile.o\
       $(OBJ)/RGISEdit.o\
       $(OBJ)/RGISEditPoint.o\
       $(OBJ)/RGISEditLine.o\
       $(OBJ)/RGISEditPoly.o\
       $(OBJ)/RGISEditGrid.o\
       $(OBJ)/RGISEditNet.o\
       $(OBJ)/RGISAnalyse.o\
       $(OBJ)/RGISAnField.o\
       $(OBJ)/RGISAnPoint.o\
       $(OBJ)/RGISAnLine.o\
       $(OBJ)/RGISAnPoly.o\
       $(OBJ)/RGISAnSampleGrid.o\
       $(OBJ)/RGISAnGrid.o\
       $(OBJ)/RGISAnNetwork.o\
       $(OBJ)/RGISAnTable.o\
       $(OBJ)/RGISAnNetStreams.o\
       $(OBJ)/RGISAnGNUXYPlot.o\
       $(OBJ)/RGISTools.o\
       $(OBJ)/RGISToolsARCImp.o\
       $(OBJ)/RGISToolsPntExp.o\
       $(OBJ)/RGISToolsGrdExp.o\
       $(OBJ)/RGISToolsGrdImp.o\
       $(OBJ)/RGISToolsNetExp.o\
       $(OBJ)/RGISToolsToPoint.o\
       $(OBJ)/RGISMetaDB.o\
       $(OBJ)/RGISDisplay.o

all: $(BIN)/$(TARGET)

install:
	cp $(BIN)/$(TARGET) $(INSTALLDIR)/bin/

uninstall:
	rm $(INSTALLDIR)/bin/$(TARGET)

clean:
	rm $(BIN)/$(TARGET) $(OBJS)

$(BIN)/$(TARGET): $(OBJS) $(SRC)/Makefile
	$(CPP) $(OBJS) $(LIBS) -o $(BIN)/$(TARGET)

$(OBJ)/%.o: $(SRC)/%.C $(INCLUDES)
	$(CPP) -o $(OBJ)/$*.o -c $(SRC)/$*.C
