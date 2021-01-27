# PepperWebClient
Display a web page with Pepper! Even though this is a very simple task with Choregraphe, various challenges may arise:

- Users attempting to access/use Choregraphe may be met with bugs or licensing issues
- Choregraphe is an extra step -- why use Choregraphe when everything can be done directly on the command line?
- The website must run continuously without being preempted or the code dying

It is worth noting that webpages may be displayed directly through the NaoQi API through the use of ```ALTabletService.showWebview```. If not packaged into an _interactive_ activity, however, Autonomous Life will automatically preempt the webview after only a few seconds of displaying the site. It is therefore optimal to display the website through a behavior running inside of an activity, as is done in this repository.

## Required Libraries
*qipkg*: ```http://doc.aldebaran.com/qibuild/beginner/qipkg/tutorial.html```

## Build Instructions

Access to a Pepper Robot is required. The robot should be on, and its IP address should be known (referred to as ROBOT_IP).

Build the activity:

```qipkg make-package pepper_webpage.pml --force```

Install the activity on the robot:

```qipkg deploy-package pepper_webpage-217edb-0.0.1.pkg --url nao@ROBOT_IP```

## Run Instructions
The activity can be run by calling the ```switchFocus``` function within the ALAutonomousLife service on the robot.
