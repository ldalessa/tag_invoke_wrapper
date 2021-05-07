# tag_invoke_wrapper
A wrapper for Eric Niebler's tag_invoke gist that adds CMake FetchContent functionality.

The actual file is pulled from 
https://gist.github.com/ericniebler/056f5459cf259da526d9ea2279c386bb, this 
just adds a CMakeLists.txt that defines a `tag_invoke_wrapper::tag_invoke`
library, provides a "tag_invoke/tag_invoke.hpp" header with a `#pragma once`,
and include's Eric's header.
