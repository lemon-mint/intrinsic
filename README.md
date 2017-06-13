
# intrinsic
Work in progress.
Provide Golang native SIMD intrinsics on x86/amd64 platform

* SSE2 doc ![](https://godoc.org/github.com/mengzhuo/intrinsic/sse2)

## usage

```golang

package main

import (
    "fmt"

    "github.com/mengzhuo/intrinsic/sse2"
)

func main() {
    src := []float32{3.14, 2.17}
    dst := []float32{2.17, 3.15}
    sse2.MAXSDm64float32(src, dst)
    fmt.Print(src, dst) //[2.17 3.15] [2.17 3.15]
}

```

## benchmarks
it will provide about 6x-7x performance enhancement.

SSE2

```
BenchmarkPMINUBByte-4         	1000000000	         2.65 ns/op	       0 B/op	       0 allocs/op
BenchmarkGeneralPMINUBByte-4   	100000000	        15.8 ns/op	       0 B/op	       0 allocs/op
BenchmarkPAND-4               	1000000000	         2.61 ns/op	       0 B/op	       0 allocs/op
BenchmarkGeneralAND-4         	100000000	        15.4 ns/op	       0 B/op	       0 allocs/op
```

## TODO

- [ ] SSE2
- [ ] SSE3
- [ ] SSSE3
- [ ] SSE4\_1
- [ ] SSE4\_2
- [ ] AVX
- [ ] AVX2
- [ ] FMA
