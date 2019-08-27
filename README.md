### Run dev application

P.S feel free to use yarn or npm

```
> yarn install
> react-native run:android
```

### Steps to reproduce the issue:
1. open app:
  - the background geolocation service will start
  - I used fake gps, but can use lockito or gpx to simulate movement
  - it will show a button 'Click here and make HTTP request'
  - it will show a text as 'is Loading false' bellow the button
  - it will show a text as 'data {}' bellow the loading text
2. start fake gps:
  - the background geolocation service will start collecting lat long
3. with the app opened or closed, disable internet connection, wait a few seconds and enabled it, than go back to the app and click on 'Click here and make HTTP request':
  - the loading text will change to 'is Loading true'
  - the data text won't change yet, it will keep showing 'data {}'
  - it is going to take a few minutes (3 - 5 minutes) until the request is executed and the data is received
  - when the data is received it will show 'is Loading false'
  - when the data is received it will show 'data { poc: null }' (its null because I'm sending an unexisting storeId in variables)

The expected behavior is to received the data almost imediatly as a normal HTTP request
