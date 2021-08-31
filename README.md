# Lua on Unikraft

This application prints "hello world from initrd" using Lua.

To configure, build and run this application you need to have [kraft](https://github.com/unikraft/kraft) installed.

Configure the application:
```
kraft configure
```

Build the application:
```
kraft build
```

And finally, run the application:
```
kraft run -i helloworld.lua
```

If you want to have more control, you can configure and run the application manually.

To configure it with the desired features:
```
make menuconfig
```

Build the application:
```
make
```

Run the application:
```
sudo qemu-system-x86_64 \
	     -kernel build/app-lua_kvm-x86_64 \
	     -initrd "helloworld.lua" \
	     -enable-kvm \
	     -nographic
```

For more information about `kraft` type ```kraft -h``` or read the [documentation](http://docs.unikraft.org).
