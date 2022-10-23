About
-----

NyoC: a Limited Self Driver (LSD) based on [openpilot](https://en.wikipedia.org/wiki/Openpilot) providing automated driving and parking assistance.

Running on PC
------

All of openpilot's services can run as normal on a PC, even without special hardware or a car. To develop or experiment with openpilot you can run openpilot on recorded or simulated data.

With openpilot's tools, you can plot logs, replay drives, and watch the full-res camera streams. See [the tools README](tools/README.md) for more information.

You can also run openpilot in simulation [with the CARLA simulator](tools/sim/README.md). This allows openpilot to drive around a virtual car on your Ubuntu machine. The whole setup should only take a few minutes but does require a decent GPU.

A PC running openpilot can also control your vehicle if it is connected to a [webcam](https://github.com/commaai/openpilot/tree/master/tools/webcam), a [black panda](https://comma.ai/shop/products/panda), and a [harness](https://comma.ai/shop/products/car-harness).


Directory Structure
------
    .
    ├── cereal              # The messaging spec and libs used for all logs
    ├── common              # Library like functionality we've developed here
    ├── docs                # Documentation
    ├── opendbc             # Files showing how to interpret data from cars
    ├── panda               # Code used to communicate on CAN
    ├── third_party         # External libraries
    ├── pyextra             # Extra python packages
    └── system              # Generic services
        ├── camerad         # Driver to capture images from the camera sensors
        ├── clocksd         # Broadcasts current time
        ├── hardware        # Hardware abstraction classes
        ├── logcatd         # systemd journal as a service
        └── proclogd        # Logs information from /proc
    └── selfdrive           # Code needed to drive the car
        ├── assets          # Fonts, images, and sounds for UI
        ├── athena          # Allows communication with the app
        ├── boardd          # Daemon to talk to the board
        ├── car             # Car specific code to read states and control actuators
        ├── controls        # Planning and controls
        ├── debug           # Tools to help you debug and do car ports
        ├── locationd       # Precise localization and vehicle parameter estimation
        ├── loggerd         # Logger and uploader of car data
        ├── manager         # Deamon that starts/stops all other daemons as needed
        ├── modeld          # Driving and monitoring model runners
        ├── monitoring      # Daemon to determine driver attention
        ├── navd            # Turn-by-turn navigation
        ├── sensord         # IMU interface code
        ├── test            # Unit tests, system tests, and a car simulator
        └── ui              # The UI
