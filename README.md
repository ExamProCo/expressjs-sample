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

When uploading to Elastic Beanstalk zip the contents of the root project
folder and include `.ebextensions`. Excluding `.git` since this could
contain sensitive credentials.

![](https://github.com/ExamProCo/expressjs-sample/blob/master/docs/zipping.jpg)

# Show your hidden files and folders
Omitting `.ebextensions` is the most common reason for failed
deployments to Elastic Beanstalk

You may need to show all hidden files and folders. On OSX you can view all hidden files and folders by pressing `Command + Shift + .`

# Credits

Space background borrowed from here:
https://codepen.io/NazarTheVis/pen/zqXMqP
