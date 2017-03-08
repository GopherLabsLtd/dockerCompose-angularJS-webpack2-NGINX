# Docker Compose + Express + AngularJS (Material - ocLazyLoad) + Webpack 2 + NGINX
![angular 1.5.9](https://img.shields.io/badge/angular-1.5.9-brightgreen.svg) ![webpack 2.2.1](https://img.shields.io/badge/webpack-2.2.1-brightgreen.svg) ![NGINX 1.11.10](https://img.shields.io/badge/NGINX-1.11.10-brightgreen.svg) ![License MIT](https://img.shields.io/badge/license-MIT-blue.svg)

This is an express server setup being built using webpack, and running lazy-loaded angular-material on the frontend.
All inside Docker.

<img src="https://raw.githubusercontent.com/preciousDev/angularMaterial-webpack2-ocLazyLoad/master/preview.gif" alt="An express app running angularJS, built through webpack and lazy-loaded assets" style="max-width: 100%;" width="1000">

### Current Webpack Configs
- Reads Sass & bundles into the final CSS 🎉
- Can make multiple bundles with multiple entries 😍
- Removes all console.log calls 🙏
- Removes all comments 👌
- Bundles CSS, JS, images, fonts & videos
- Excracts bundles to files instead of inline (all minified) 🔥

**The `docker-compose-alpine.yml` file currently only supports alpine for NGINX, since sass-loader is still problematic on alpine** 😞

### Usage
**1-** Clone the repo
```shell
git clone https://github.com/preciousDev/dockerCompose-angularJS-webpack2-NGINX.git
```

**2-** Create a docker-machine
```shell
docker-machine create --driver virtualbox test
```

**3-** Switch to the new machine
```shell
docker-machine env test
```

**4-** Run this command to configure your shell:
```shell
eval $(docker-machine env test)
```

**5-** Build through docker-compose:
```shell
docker-compose build --no-cache
```

**6-** After the build is finish, bring the containers up using:
```shell
docker-compose up
```

<img src="https://raw.githubusercontent.com/preciousDev/dockerCompose-angularJS-webpack2-NGINX/master/dockercomposeup.jpg" alt="Node.js app built through Webpack2, running AngularJS, load-balanced by NGINX inside Docker Containers ☁️️ 🐳" style="max-width: 100%;" width="600">

### Important Note
Ideally you'd want to `cd` into the `nodeapp` folder, run webpack-dev-server and keep applying your changes.
Once you're done, you would build out the containers.

- **To Run webpack-dev-server**
```shell
cd nodeapp && npm run dev
```

- **Build using webpack and run the express server**
```shell
cd nodeapp && npm run prod
```

- **Run the express server without building**
```shell
cd nodeapp && npm start
```

### Contributing
If you feel that something is missing, make an issue! 🙂
If you want do add something, just make a Pull Request.

# License
MIT License

Copyright (c) 2017 preciousDev

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
