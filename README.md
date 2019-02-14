# Welcome to RocketMiX website!

This git repo contains all web content we publish on rocketmix.github.io.
If you need to switch to project's source code, go to https://github.com/rocketmix/rocketmix.source

## Development technologies

This site is developed using Bootstrap 4. All main resources (excepted images and custom js) are delegated to common CDN. Thus, Bootstrap and JQuery are not duplicated here. This site has to be responsive to be easily displayed on mobile devices such as smartphones. 

## Specific integration of flying stars (particle.js)

We integrated particle.js to display starts on the main content. To perform that, We made an hack to Bootstrap grid with a few lines of javascript.

Go to js/particles-init.js

You will see that we change height of #particles-container div to fit the current viewport height. This allows to display stars all over the current viewport (Viewport is the part of the screen which is available for the website - removing address bar, tab bar, etc...).
Open index.html. You should see that we declare a #particle div which contains stars. Texts and logos are contained in a standard Bootstrap div called #particles-content.

Then, by using css relative and aboslute position, we declared in css/styles.css that #particle and #particle-content as two overlaped layers (position abolute at 0:0 inside #particles-container. And that all! We have text and logo in front of stars.

Look at this marvelous CSS hack :

```
#particles-container {
    position: relative;
    min-height: 700px;
    width: 100%;
    max-width: 100%;
    padding-right: 0px;
    padding-left: 0px;
    background-color: black;
}

@media (max-width: 575px) {
    #particles-container {
        min-height: 500px;
    }
}

#particles, #particles-content {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin-left: 0;
    margin-right: 0;
}
#particles-content {
    z-index: 10;
    padding-top: 100px;
}
```

## How to contribute ?

Please clone this repo and make a pull request. Many thanks for your contribution.
