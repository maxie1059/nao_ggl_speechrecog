# INTEGRATION OF GOOGLE SPEECH RECOGNITION IN NAO ROBOT

**PRE-REQUISITE**

In this integration, you should already know how to bringup NAO with ROS. If not, [this](https://github.com/maxie1059/nao_ros/blob/master/README.md) is where you learn it.

**INTEGRATION**

After sucessfully bringing-up, put the two scripts I included in the repository into any package and rosrun it.
```
rosrun <package> <script>
```
For example:
```
rosrun hello_world reac
rosrun hello_world recog
```

*Note:* the dialog that NAO says can only be viewed in Choregraphe

**DISADVANTAGES**

- In the 'recog' script, the ambient noise will be calibrated first in order to recognize if the user is speaking. That also means whenever there are some new unwelcoming noises enter during the audio recording, the recognizing process will take longer and less accurate. The only solution for this problem is that the room must stay as quiet as when it was calibrated.

- This error will happen after some good recognizing run:
  ```
  No JSON object could be decoded.
  ```
  The error will disappear after 2-5 minutes. Suggestions for solution are:
  - Create or sign in a Google Account and register for Google Cloud Speech API for a credential key. The normal Google Speech Recognition uses a general key and it can be revoked by Google anytime (or someone could be using it at the same time). 
  *Note*: The Googe Speech Recognition in 'recog' script will have to change. For reference, visit [PyPi](https://pypi.org/project/SpeechRecognition/).
  - [Code fixes](https://stackoverflow.com/questions/23392107/no-json-object-could-be-decoded-with-google-api) in 'recog' script. This solution is unsure but can be taken into consideration.
