
import sys
from pubnub import Pubnub

pubnub = Pubnub(publish_key='pub-c-396e9fbf-4e09-4a9b-b335-e8c25fe6bd24', subscribe_key='sub-c-0608f17c-9d0d-11e6-a0c0-0619f8945a4f')

channel = 'hello-pi'

data = {
  'username': 'Your name',
  'message': 'Hello World from Pi!'
}

def callback(m):
  print(m)

pubnub.publish(channel, data, callback=callback, error=callback)
