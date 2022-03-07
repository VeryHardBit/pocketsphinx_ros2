# pocketsphinx-ros2
pocketsphinx binding to ROS2
pocketsphinx is a speech recognition library for Python. So this ROS package will make pocketsphinx bind to ROS system.

In serious of Working in Progress


## Dependencies (Likely to change)
- pocketsphinx - 
    https://pypi.org/project/pocketsphinx/
    https://github.com/cmusphinx/pocketsphinx-python
- pyttsx3 - https://pypi.org/project/pyttsx3/
- espeak - `$ sudo apt-get update && sudo apt-get install espeak`
- rhvoice
- festival - `$ sudo apt-get install festival`
- pico2wave - `$ sudo apt-get install libttspico-utils`


## topic in used


## testing
[robot come here]

Hello,What would you like to drink?

[Drink name]

Ok,I will be back with your drink.

Here is your drink.

[Thank you]

You're welcome.


# Node
- pocketsphinx_speech_srv_node (speech_recog_srv.py)
    - create service name `speech_recog_output`
    - to run `ros2 run pocketsphinx_ros speech_recog_srv`
    - to test `$ ros2 service call /speech_recog_output pocketsphinx_ros_interfaces/srv/SpeechRecog {}`

- pocketsphinx_tts_srv_node (tts_srv.py)
    - create service name `tts_input`
    - to run `$ ros2 run pocketsphinx_ros tts_srv`
    - to test `$ ros2 service call /tts_input pocketsphinx_ros_interfaces/srv/TTS {}`
<br><br><br>

- pocketsphinx_speech_pub_node : `$ ros2 run pocketsphinx_ros speech_recog_pub`
    - get sound from microphone.do speech recognition and publish to topic `/speech_recognition/output`.

- pocketsphinx_tts_node : `$ ros2 run pocketsphinx_ros tts`
    - get string from topic `/speech_tts/input` and do text to speech with that string.