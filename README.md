# expressjs-sample

How to build this skeleton app from scracth


Install the express js generator

```
npm install -g express-generator
```

Run generator and when promoted press y
```
express
```

Install all dependencies
```
npm i
````

Start server in development mode
```
DEBUG=expressjs-sample:* npm start
```

Go to `https://localhost:3000` within your web browser

create the following files:

.ebextensions/nodecommand.config
```
  aws:elasticbeanstalk:container:nodejs:
    NodeCommand: "npm start"
```

.ebextensions/staticfiles.config
```
option_settings:
  aws:elasticbeanstalk:container:nodejs:staticfiles:
    /public: /public
```

To upload to S3 upload the contents of your web-app (not the folder
itself), ensure you turn on hidden files and include .ebextensions in
the zip


# Credits

Space background borrowed from here:
https://codepen.io/NazarTheVis/pen/zqXMqP
