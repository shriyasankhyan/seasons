This react based application tells the hemisphere to which the user belongs. 
## 4 cases
1. If the user is in the northern hemisphere and the current month is between October and March, it shows that it is winter season.
2. If the user is in the northern hemisphere and the current month is between March and October, it shows that it is winter season.
3. If the user is in the southern hemisphere and the current month is between March and October, it shows that it is summer season.
4. If the user is in the southern hemisphere and the current month is between October and March, it shows that it is summer season.
For this , we first need to know the user's physical location.
Secondly , we need to determine the current month as on the basis of the month and location , this app is going to tell the hemisphere in which the user is living.
Lastly, we need to change the text and styling of the react based on user's location and month.

#### For finding user's location 
We have used MDN Geolocation API.The Geolocation API allows the user to provide their location to web applications if they so desire. For privacy reasons, the user is asked for permission to report location information.
WebExtensions that wish to use the Geolocation object must add the "geolocation" permission to their manifest. The user's operating system will prompt the user to allow location access the first time it is requested.

The developer can now access this location information in a couple of different ways:

### Geolocation.getCurrentPosition()
Retrieves the device's current location.
Geolocation.watchPosition(): Registers a handler function that will be called automatically each time the position of the device changes, returning the updated location.
In both cases, the method call takes up to three arguments:

A mandatory success callback: If the location retrieval is successful, the callback executes with a GeolocationPosition object as its only parameter, providing access to the location data.
An optional error callback: If the location retrieval is unsuccessful, the callback executes with a GeolocationPositionError object as its only parameter, providing access information on what went wrong.
An optional object which provides options for retrieval of the position data.

## Note
This API may be unavailable in China. So if you are from China , it may show wrong results or throw an error.

### How this app works ?
1. JS file loaded by browser.
2. App component gets created.
3. We call geolocation service.
4. App return JSX, gets rendered to page as HTML.
5. We get result of geolocation which takes more time. So we have to tell the component to rerender itself with this new information.

We will use State so that if location changes our app rerenders itself.
