# sdk-android
Lovense SDK for Android

It is highly recommended to use Android Studio to develop the application.

Download & unzip the SDK

Download the SDK

Add the permission in your AndroidManifest.xml

Add the libraries to your project

Make sure you have added the lovense.jar to your classpath

Connect Lovense Toys

There are only 6 steps to use Lovense SDK

1. Pass your token into Lovense class in your Activity


    Lovense.getInstance(context).setDeveloperToken("Your Token");
2. Search the toy(s) over Bluetooth


    List<LovenseToy> toys=new ArrayList<>();
    Lovense.getInstance(context).searchToys(new OnSearchToyListener() {
        @Override
        public void onSearchToy(LovenseToy toy) {
            toys.add(toy);
        }
    }, new OnErrorListener() {
        @Override
        public void onError(LovenseError error) {

        }
    });
3. Save the toy(s)


    Lovense.getInstance(context).saveToys(toys, new OnErrorListener()
    {
        @Override
        public void onError(LovenseError error) {

        }
    });
4. Retrieve the saved toy(s)


    Lovense.getInstance(context).listToys(new OnErrorListener() {
        @Override
        public void onError(LovenseError error) {
        }
    });
5. Connect the toy(s)


      Lovense.getInstance(context).connectToy(toyId, new OnConnectListener() {
        @Override
        public void onConnect(String status) {

            switch (status) {
                case LovenseToy.STATE_CONNECTED:
                    break;
                case LovenseToy.STATE_CONNECTING:
                    break;
                case LovenseToy.STATE_FAILED:
                    break;
            }
        }
      }, new OnErrorListener() {
        @Override
        public void onError(LovenseError error) {

        }
      });
  
6. Send commands to the toy(s)


     Lovense.getInstance(context).sendCommand(toyId, "Vibrate", 5, new OnErrorListener() {
        @Override
        public void onError(LovenseError error) {

        }
     })
 
For API documentation, please click here 
