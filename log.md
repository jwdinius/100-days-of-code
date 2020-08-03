# 100 Days Of Code - Log
### Proposed Plan
* Implement graph-based solver in my [personal project](https://github.com/jwdinius/nmsac)
* Contribute to [navigation2](https://github.com/ros-planning/navigation2)
* Contribute to [ros2 middleware project](https://github.com/ros2/rmw)
* Understand, and develop models/implementations for, biologically-inspired vision
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

### Day 2: July 27, Monday

**Today's Progress**:
* Updated documentation in my personal project and tagged a new release
* Got my git on - lots of rebasing, squashes, and release tagging.

**Thoughts**
My git was pretty rusty, so I'm glad I got to circle back and revisit some of these skills.  I didn't get much coding done today, but I really wanted to resolve an outstanding issue that I had been meaning to get to for awhile now.  I feel like I can move on to the more exciting dev tasks I have lined up over the next few weeks.  Documentation is an oft-neglected aspect of good software development, so I feel justified in using this time towards 100 Days of Code.

**Link(s) to work**
1. [Pull request](https://github.com/jwdinius/nmsac/pull/6) - _this references the actual documentation commit_
2. [tagged release v0.2.0](https://github.com/jwdinius/nmsac/pull/6)

### Day 3: July 28, Tuesday

**Today's Progress**:
* Read first chapter in [this book](https://www.amazon.com/Understanding-Vision-Theory-Models-Data/dp/0198829361)

**Thoughts**
I spent most of the day working through a frustrating dev issue with some software I was writing.  I just didn't have the energy to code anymore after finishing work for the day.  The compromise I reached was to read a reference that helps me to understand physiologically visual perception.

**Link(s) to work**
_none today_

### Day 4: July 29, Wednesday

**Today's Progress**:
* Attended first RMW middleware working group (kick-off)

**Thoughts**
For me, 100DaysOfCode is about more than just banging out code.  I want to spur myself on to contributing more to open source projects; ros-based projects in particular.  Committing to 100DaysOfCode made getting out of my comfort zone and attending the working group meeting easier for me.

**Link(s) to work**
1. [meeting notes](https://docs.google.com/document/d/1pdPdcBk2YcR0IpmslDN07WGbhNU3WIaz-UBh2sDW_P0/edit#heading=h.cj1akj1l2p2i)

### Day 5: July 30, Thursday

**Today's Progress**:
* none, due to a technical issue

**Thoughts**
We have been having a heatwave in SoCal and a brownout resulted in my display getting messed up on my workstation.  I spent today's time trying to get it up-and-going again, with not luck in Linux.  Fortunately, I have dual boot with Windows 10, so I was able to verify that my Nvidia card was still functional via by updating the driver, restarting, and looking at the the Nvidia Control Panel.

**Link(s) to work**
_N/A_

### Day 6: July 31, Friday

**Today's Progress**:
* Fixed Nvidia Linux graphics driver on my workstation

**Thoughts**
This issue blew away all available time I had for side projects, but now I have a functional workstation again.  Before committing to the 100 Days Of Code, I would have probably let this issue sit for multiple days (or weeks).  Having made the commitment, I resolved the issue much more quickly and I am happier for it.

**Link(s) to work**
_N/A

### Day 7: August 1, Saturday

**Today's Progress**:
* Worked through [Fast DDS docs](https://fast-dds.docs.eprosima.com/en/latest/)

**Thoughts**
This is a combination of work and play for me:  I really want to understand networking stacks for robotics much better, both for personal and professional gain, so I went through the verbose documentation, example code, and tried to identify configuration properties for shuttling large datastreams (like camera images) between publishers and subscribers.

**Link(s) to work**
I was able to nail down 4 key components with configurable properties for modifying Quality-of-Service in Fast DDS:
* DomainParticipantQos
* TopicQos
* Publisher(Subscriber)Qos
* DataWriter(Reader)Qos

### Day 8: August 2, Sunday

**Today's Progress**:
Resolved 3 issues in my personal [project](https://github.com/jwdinius/nmsac)
* Reconsidered potential change; I looked at my implementation, the scope of the pull request, and decided to close the issue
* Added conditional generators to allow CMake to setup desired build steps at configure-time
* Add continuous integration (including README badge)

**Thoughts**
I had been putting off these, let's call them, "niceties" because I wasn't sure of the amount of work that would be required.  For the conditional generator work, I hadn't used this feature in CMake >3.0 before and the documentation I found made it look pretty daunting.  Fortunately, though, I found the book Professional CMake, and the examples presented in that book were really helpful!  Similarly, for the CircleCI integration, I haven't had to setup anything similar for quite awhile; I had setup a travis ci job in the past, and CircleCI looked kind of similar.  I was glad to see that, following the reference from [nlohmann::json](https://github.com/nlohmann/json) (one of my favorite libraries to use as a reference), setting up a CircleCI pipeline was really easy.  _I was even able to use my development docker image as a base for the CircleCI container!_

**Link(s) to work**
1. https://github.com/jwdinius/nmsac/pull/10
2. https://github.com/jwdinius/nmsac/pull/12
