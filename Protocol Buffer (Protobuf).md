---
aliases : [protobuf, Protobuf]
---
```protobuf
syntax = "proto3";

message MyMessage {
	int32 id = 1;
	string first_name = 2;
	bool is_validated = 3;
}
```

Protocol Buffers is defined by a .proto text file
Human readable format. 

Google use it for almost all their internal applications.
They have over 48,000 Protobuf messages types in 12,000 .proto files

### Advantages
- Data is fully typed
- Data is compressed automatically
- Schema (defined using .proto file) is needed to generate code and read the data
- Documentation can be embedded in the schema
- Data can be read across any languages
- Schema can evolve over time.
- 2-10x smaller, 20-100x faster than XML.
- Code is generated automatically.

### Disadvantages
- Protobuf support for some languages might be lacking
- Can't open the serialized data with a text editor 