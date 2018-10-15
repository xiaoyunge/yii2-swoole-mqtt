MQTT For Yii2 Base On Swoole 4
==============================
MQTT server for Yii2 base on swoole 4,  Resolve topic as a route reflect into controller/action/param, And support redis pub/sub to trigger async task from your web application

Installation
------------
Install Yii2: [Yii2](https://www.yiiframework.com).

Install swoole: [swoole](https://www.swoole.com), recommend version 4+.

Other dependency: php-redis extension.

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist immusen/yii2-swoole-mqtt "*"
```

or add

```
"immusen/yii2-swoole-mqtt": "*"
```

to the require section of your `composer.json` file.


Test or Usage
-------------

```
#after installation, cd project root path, e.g. cd yii2-advanced-project/
mv vendor/immusen/yii2-swoole-mqtt/example/mqtt ./
mv vendor/immusen/yii2-swoole-mqtt/example/mqtt-server ./
chmod a+x ./mqtt-server
./mqtt-server
#or coding in ./mqtt/controllers
```

Test client: MQTTLens, MQTT.fx

Example:
--------
Case A: Subscribe/Publish

> 1, subscribe topic: room/count/100011

> 2.1, mqtt publish: every time publish topic: room/join/100011, the subscribe side will get count+1, or publish topic: room/join/100011 get count -1.

> 2.2, redis pulish: every time $redis->publish('async', 'room/join/100011'), the subscribe side will get count+1, or $redis->publish('async', 'room/join/100011') get count -1.

Case B: Publish(Notification Or Report)

> mqtt publish topic: report/coord/100111 and payload: e.g. 110.12345678,30.12345678,0,85

MQTT
----

About MQTT: [MQTT Version 3.1.1](http://docs.oasis-open.org/mqtt/mqtt/v3.1.1/mqtt-v3.1.1.html)

Thanks:
------

[yii2](https://github.com/yiisoft/yii2)

[swoole](https://github.com/swoole/swoole-src)

[xavier-chen](https://github.com/xavier-chen/swoole_mqtt_php)


# yii2-swoole-mqtt