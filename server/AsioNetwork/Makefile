ROOT_DIR:=..

include $(ROOT_DIR)/Makefile.include

MODULES:=\
	AsioNetwork.o \
	IoHandler.o \
	NetObject.o \
	Session.o \
	SessionList.o \
	SessionPool.o

INCLUDE:=-I. -I..
TARGET_LIB:=AsioNetwork.so
DEPEND_LIB:=$(BASEROOT_DIR)/$(BIN_DIR)/$(BUILD_FLAG)/Utility.so libboost_date_time.so libboost_regex.so libboost_system.so libboost_thread.so

all: $(TARGET_LIB)

$(TARGET_LIB) : $(DEPENDENCIES)
	@$(ECHO) $(STR_SHARED)
	@$(CC) $(CSHARED) $(TARGET_LIB) *.o -L$(ROOT_DIR)/$(BIN_DIR) $(DEPEND_LIB)
	@$(ECHO) $(STR_COPY)
	@$(CP) $(TARGET_LIB) $(ROOT_DIR)/$(BIN_DIR)/$(BUILD_FLAG)

%.o: %.cpp
	@echo $(STR_COMPILE): $@ 
	@$(CC) $(CMODULE) $< $(INCLUDE)