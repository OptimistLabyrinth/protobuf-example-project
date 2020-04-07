.PHONY: all

all: cpp

cpp: add_person_cpp list_people_cpp

clean:
	rm -f add_person_cpp list_people_cpp addressbook.pb.h addressbook.pb.cc

protoc_middleman: addressbook.proto
	/home/ksyoo/ksyooF/third_party/protobuf-3.2.0/bin/protoc --cpp_out=. addressbook.proto

add_person_cpp: protoc_middleman add_person.cc
	g++ -std=c++98 \
		add_person.cc addressbook.pb.cc -o add_person_cpp \
		-I . -I /home/ksyoo/ksyooF/third_party/protobuf-3.2.0/include \
		-L /home/ksyoo/ksyooF/third_party/protobuf-3.2.0/lib \
		-l protobuf \
		-Wl,-rpath /home/ksyoo/ksyooF/third_party/protobuf-3.2.0/lib

list_people_cpp: protoc_middleman list_people.cc
	g++ -std=c++98 \
		list_people.cc addressbook.pb.cc -o list_people_cpp \
		-I . -I /home/ksyoo/ksyooF/third_party/protobuf-3.2.0/include \
		-L /home/ksyoo/ksyooF/third_party/protobuf-3.2.0/lib \
		-l protobuf \
		-Wl,-rpath /home/ksyoo/ksyooF/third_party/protobuf-3.2.0/lib
