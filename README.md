# mry
Open Source Memory Editing Library


## Initialize:
```
using mry;
mem m = new mem();
m.OpenProcess("GTA5");
```

## Read Memory

##### Read Memory from Address:
```
string address = "0x7fffffffffff";
int value = m.memory(address).Get<int>();
```

##### Read Memory from Pointer
```
long ptr = 0x2DAFB50;
float value = m.memory(ptr).Get<float>();
```

##### Read Memory from Pointer + Offset
```
long ptr = 0x2DAFB50;
long offset = 0x80;
double value = m.memory(ptr, offset).Get<double>();
```

##### Read Memory from Pointer + Offset Array
```
long ptr = 0x2DAFB50;
long[] offsets = new long[] { 0x80, 0x10 };
long value = m.memory(ptr, offsets).Get<long>();
```

##### Read Unicode String from Pointer + Offset  
```
long ptr = 0x2DAFB50;
long offset = 0x80;
string value = m.memory(ptr, offset).GetString(size = 255, unicode = true);
```

##### Read 20 Bytes from Pointer + Offset Array
```
long ptr = 0x2DAFB50;
long[] offsets = new long[] { 0x80, 0x10 };
byte[] value = m.memory(ptr, offsets).Get<bytes>(20);
```


## Write Memory

##### Write to Address:
```
string address = "0x7fffffffffff";
m.memory(address).SetInt(1234);
```

##### Write to Pointer
```
long ptr = 0x2DAFB50;
float value = m.memory(ptr).SetFloat(1234.4321);
```

##### Write to Pointer + Offset
```
long ptr = 0x2DAFB50;
long offset = 0x80;
m.memory(ptr, offset).SetDouble(12.321879237498);
```

##### Write to Pointer + Offset Array
```
long ptr = 0x2DAFB50;
long[] offsets = new long[] { 0x80, 0x10 };
m.memory(ptr, offsets).SetLong(long.MaxValue);
```

##### Write Unicode String to Pointer + Offset  
```
long ptr = 0x2DAFB50;
long offset = 0x80;
string value = "~abcdef~";
m.memory(ptr, offset).WriteString(value, unicode = true);
```

##### Write Bytes to Pointer + Offset Array
```
long ptr = 0x2DAFB50;
long[] offsets = new long[] { 0x80, 0x10 };
byte[] bytes = new byte[] { 0x80, 0x10 }
m.memory(ptr, offsets).SetBytes(bytes);
```
