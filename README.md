![Kitura](https://raw.githubusercontent.com/IBM-Swift/Kitura/master/Documentation/KituraLogo.png)

![Linux](https://img.shields.io/badge/os-linux-green.svg?style=flat)
![Mac OS X](https://img.shields.io/badge/os-Mac%20OS%20X-green.svg?style=flat)
![Apache 2](https://img.shields.io/badge/license-Apache2-blue.svg?style=flat)
[![Join the chat at https://gitter.im/IBM-Swift/Kitura](https://badges.gitter.im/IBM-Swift/Kitura.svg)](https://gitter.im/IBM-Swift/Kitura?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

**Server Side Swift example with InstaTrip API based on IBM Kitura**

This example is based on the Bluemix starter application for IBM Kitura web framework and HTTP server.
Below you would find:
- the sample Swift server side code;
- playing with Swift in the Swift Sandbox!
- it is enough to just click to deploy the Swift Server Side app on IBM Bluemix cloud;
- you might edit the code, redeploy, and check the logs direct from your browser;
- further reading, and my blog, of course.

[![youtube from blumarek.blogspot.com](https://pbs.twimg.com/media/ClK8AFDUoAEuRVN.jpg:large)](https://youtu.be/Rok6545sqHs)

Check the video for the explanations

##The Swift Server Side Sample
The Swift sample code for IBM Kitura Web Server used in our example is based on the following API response with the JSON message:

```Swift
import Kitura

let router = Router()

// getting the 'cognitive' travel arrangements for Hawaii
router.get("/HNL") {
    request, response, next in
    response.send("{price : '$670'," + " trip : 'Round Trip'," + " FROM : 'SFO', TO : 'HNL'}")
    next()
}

Kitura.addHTTPServer(onPort: 8090, with: router)
Kitura.run()
```
It is elegant, isn't it? IBM Kitura web server philosophy is inspired by node.js' Express.js framework.

##Play with Swift in your web browser!
Check the link [http://ibm.biz/SwiftSandbox](http://ibm.biz/SwiftSandbox) .
In this web based IBM Swift Sandbox - the code editor you might learn & try the basic Swift constructs - and share them with your social network, if you feel like becoming known Swift coder.

## IBM Kitura sample - run Swift web server in the Bluemix cloud just under 5 minutes
_Using the Deploy to Bluemix magic button_
Clicking on the button below deploys this sample application to Bluemix. The `manifest.yml` file [included in the repo] is parsed to obtain the name of the application and configuration details. 

*click - deploy on Bluemix (free of charge trail for 30 days of fun)*

[![Deploy to Bluemix](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy)

Once deployment to Bluemix is completed, you should access the route assigned to your application using the web browser of your choice. You should see the Kitura welcome page! In addition you might want to do following things straight from your browser:
- code straight in your browser,
- and deploy to cloud and check logs from the browser.

Note that the [Bluemix buildpack for Swift](https://github.com/IBM-Swift/swift-buildpack) is used for the deployment of next-killer-app-swift to Bluemix. This buildpack is currently installed in the following Bluemix regions: US South, United Kingdom, and Sydney.

## Alternatively download IBM Kitura and setup up your Swift dev environment in your linux or xos (Macos)
You can run Swift on Linux, or xos. It is very simple process. You download the release of the Swift, and add it to the environment. Follow the following steps:

*downloading Swift*
This version of Kitura-Starter-Bluemix works with the DEVELOPMENT-SNAPSHOT-2016-05-03-a version of the Swift binaries. You can download this version of the Swift binaries by following this [link](https://swift.org/download/). Compatibility with other Swift versions is not guaranteed.

*Clone, build, and run*
1. Clone this repo using `git clone https://github.com/blumareks/next-killer-app-swift.git` and go to the root folder using `cd next-killer-app-swift`. Please do not use the GitHub `Download ZIP` button as a way to clone this repo.

2. Compile and execute the server app using: `make run`. Once the server starts, you should see the message _Listening on port 8090_. The executable file is located in the `.build/debug` directory: `./.build/debug/next-killer-app-swift`.

3. Open your browser at [http://localhost:8090](http://localhost:8090).

4. Access static content using the following URL:[http://localhost:8090/static](http://localhost:8090/static).

5. Access our example by getting this URL:[http://localhost:8090/HNL](http://localhost:8090/HNL)

## Further reading
- [another DeveloperWorks Swift Kitura sample](https://developer.ibm.com/swift/2016/02/22/building-end-end-cloud-apps-using-swift-kitura/)
- [https://github.com/IBM-Swift/Kitura](https://github.com/IBM-Swift/Kitura) - for our roadmap and some IBM Kitura tutorials.
- [https://github.com/IBM-Swift/Kitura-Starter-Bluemix](https://github.com/IBM-Swift/Kitura-Starter-Bluemix) - the original Kitura example page
- my blog: [blumareks.blogspot.com](http://blumareks.blogspot.com)

Follow me on Twitter: [@blumareks](https://twitter.com/blumareks)

## Some more in detail reading
Kitura-Starter-Bluemix is a [Kitura](https://github.com/IBM-Swift/Kitura) based server application that you can use as a starting point to get your own Kitura application up and running on Bluemix. After cloning this GitHub repo to your local system, you can deploy this application to Bluemix right away. If you'd also like to run Kitura-Starter-Bluemix locally, then see the instructions for installation on [OS X ](https://github.com/IBM-Swift/Kitura#installation-os-x) or installation on [Linux](https://github.com/IBM-Swift/Kitura#installation-linux-apt-based) for details on system level dependencies you may need before attempting to execute this app.

## ALternatively manually pushing the application to Bluemix
*Using the Cloud Foundry command line*
You should have the Cloud Foundry & Bluemix command line installed on your system and you should be already logged on to Bluemix before you attempt the following steps.
```shell
bluemix api https://api.ng.bluemix.net
bluemix login -u your-email@examaple.com -o your-email@examaple.com -s dev
```

1. From the root folder of this repo on your local system, execute `cf push`.
The command would use the `manifest.yml` to deploy the code and start the service on IBM Bluemix. For further details on the structure of the `manifest.yml` file, see the [Cloud Foundry documentation](https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html#minimal-manifest).


2. Once the application is pushed to and running on Bluemix, you can access your application route to see Kitura's welcome page on your browser.

## Kitura Wiki
Feel free to visit our [Wiki](https://github.com/IBM-Swift/Kitura/wiki) 

## License
The Kitura-Starter-Bluemix sample app is licensed under Apache 2.0. Full license text is available in [LICENSE](LICENSE.txt).
