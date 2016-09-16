# RPI Mosquitto

* Master : [![Circle CI](https://circleci.com/gh/zeiot/rpi-mosquitto/tree/master.svg?style=svg)](https://circleci.com/gh/zeiot/rpi-mosquitto/tree/master)
* Develop : [![Circle CI](https://circleci.com/gh/zeiot/rpi-mosquitto/tree/develop.svg?style=svg)](https://circleci.com/gh/zeiot/rpi-mosquitto/tree/develop)

Docker image of [Mosquitto][] to use on a [Raspberry PI][].

Exposes Port `1883` (MQTT) and `9001` (Websocket MQTT)

Configure binfmt-support on the Docker host (works locally or remotely, i.e: using boot2docker):

    $ docker run --rm --privileged multiarch/qemu-user-static:register --reset

Then you can run an armhf image from your x86_64 Docker host :

    $ make run version=1.4

Or build :

    $ make build version=1.4


# Usage

Launch Mosquitto :

    $ make run version=1.4

In Terminal window 1 type:

    $ mosquitto_sub -v -p 1883 -t rpi/test

In Terminal window 2 type:

    $ mosquitto_pub -d -p 1883 -t rpi/test -m "Hello Jarvis!"
    Client mosqpub/4785-nlamirault sending CONNECT
    Client mosqpub/4785-nlamirault received CONNACK
    Client mosqpub/4785-nlamirault sending PUBLISH (d0, q0, r0, m1, 'k8s/test', ... (13 bytes))
    Client mosqpub/4785-nlamirault sending DISCONNECT


# Supported tags

* [![](https://images.microbadger.com/badges/version/zeiot/rpi-mosquitto.svg)](http://microbadger.com/images/zeiot/rpi-mosquitto "Get your own version badge on microbadger.com")


## License

See [LICENSE](LICENSE) for the complete license.


## Changelog

A [ChangeLog.md](ChangeLog.md) is available.


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>


[Raspberry PI]: https://www.raspberrypi.org/
[Mosquitto]: https://mosquitto.org/
