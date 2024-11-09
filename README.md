This is just a direct copy of boost example from `https://github.com/boostorg/beast/tree/develop/example/websocket/client/async`, added CMakeLists.txt. 

To run: 
- `cmake -S . -B build -G Ninja -DCMAKE_EXPORT_COMPILE_COMMANDS=1 -DCMAKE_BUILD_TYPE=Debug`
- `ninja -C build`
- `source invoke.sh`

Potentially useful command is `strace -f -e trace=network --output=log1.txt ./build/example_beast_client websocket-echo.com 80  "Hello, world!"`
