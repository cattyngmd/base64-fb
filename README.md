# base64-fb

simple implementation of base64 encoder and decoder in Fireball programming language

## example

```
import std::os::{stdout};
import base64::{encode_base64_str, decode_base64_str, Alphabet};

func main() {
    var out = stdout();

    var encoded = encode_base64_str("hello world", Alphabet::Standard).unwrap();
    out.write(encoded.as_bytes()); // aGVsbG8gd29ybGQ=
    out.write("\n");

    var decoded = decode_base64_str(encoded, Alphabet::Standard).unwrap();
    out.write(decoded.as_bytes()); // hello world
    out.write("\n");

    encoded.free(); // lol
    decoded.free();
}
```
