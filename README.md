# timer.h

Simple timer with microsecond resolution.

It uses `gettimeofday()`, so is not portable to non-Unix
platforms.

# Installation

Install it with [clib](https://github.com/clibs/clib):

    $ clib install clibs/timer

If you want to use it manually, copy `src/timer.h` and
`src/timer.c` to your project directory and include them on your Makefile.

# Usage

This module defines a `timer_t` structure that can count
deltas from microseconds up to hours.

```c
#include "timer.h"

int main()
{
    timer_t timer;
	timer_start(&timer);

    /* do whatever you want */

    timer_pause(&timer);

    /* call one of the several delta functions: */
    timer_delta_us(&timer);
    timer_delta_ms(&timer);
    timer_delta_s(&timer);
    timer_delta_m(&timer);
    timer_delta_h(&timer);
}
```

The file `test.c` shows a full example.

# License

(The MIT License)

Copyright (c) 2011,2013 Alexandre Dantas <eu@alexdantas.net>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

