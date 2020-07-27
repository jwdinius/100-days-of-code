# 100 Days Of Code - Log
### Proposed Plan
* Implement graph-based solver in my [personal project](https://github.com/jwdinius/nmsac)
* Contribute to [navigation2](https://github.com/ros-planning/navigation2)
* (more to come)

### Day 1: July 26, Sunday

**Today's Progress**:
* Committed to the challenge.
* Worked through an issue with pybind11 modules:  _I passed numpy arrays to my function interface by using index slicing (i.e. array[:3, :]).  Long story short: the c++ runtime did not like this!  I found a workaround by just using numpy.copy to create a new copy of the original array, with the desired index range._
* Pushed two commits to https://github.com/jwdinius/nmsac: got python bindings to work (with pybind11 and some mods to a lib called carma)
* resurrected a handy build-all script and it made example reproduction a snap!

**Thoughts** pybind11 shows a lot of nice improvements over Boost.Python.  Namely,
* wrapping functions is a snap:  I didn't even have to export argument type etc... in the construction of the pybind11 module
* wrapping structured data types was as thin as could be hoped for.  With Boost.Python, I recall having to create a child class or custom class that wrapped the original struct/class, but pybind11 allows for exposing the data directly.  Super cool!
* working with numpy arrays going from python-to-c++ is so easy!
It's not all sunshines and gumdrops though, it took me most of yesterday to get up-and-running.  I'm excited to use this more though!

**Link(s) to work**
1. [Pull request](https://github.com/jwdinius/nmsac/pull/8) - check the commits, yo
