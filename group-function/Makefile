#
# (C) 2009-2015, Kees Verruijt, Harlingen, The Netherlands.
#
# This file is part of CANboat.
#
# CANboat is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# CANboat is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with CANboat.  If not, see <http://www.gnu.org/licenses/>.
#

PLATFORM=$(shell uname | tr '[A-Z]' '[a-z]')-$(shell uname -m)
TARGETDIR=../rel/$(PLATFORM)
COMMAND=$(TARGETDIR)/command-group-function
REQUEST=$(TARGETDIR)/request-group-function
TARGETS=$(COMMAND) $(REQUEST)

all: $(TARGETS)

$(COMMAND): command.c ../common/common.c ../common/common.h
	$(CC) $(CPPFLAGS) $(CFLAGS) $(LDFLAGS) -o $(COMMAND) -I../common command.c ../common/common.c $(LDLIBS$(LDLIBS-$(@)))

$(REQUEST): request.c ../common/common.c ../common/common.h
	$(CC) $(CPPFLAGS) $(CFLAGS) $(LDFLAGS) -o $(REQUEST) -I../common request.c ../common/common.c $(LDLIBS$(LDLIBS-$(@)))

clean:
	-rm -f $(TARGETS) *.elf *.gdb

