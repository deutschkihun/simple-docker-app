Hello

**How to use this project file**

1. use git clone or download this file on your local pc
2. open this file with editor (ex :VScode,sublimeText,Atom.... whatever you want)
3. compile "npm install" in terminal for frontend dependencies
4. create git repository and push this project in github repository
5. Go to travis CI (please login with your github account, otherwise travis-CI can't take your github repository)
6. activate repository -> add ACCESS_KEY_ID and SECRET_ACCESS_KEY from AWS elasticbeanstalk
7. trigger build
8. automatically connected with AWS elasticbeanstalk according to .travis.yml

### Caution

make sure that your .travis.yml has correct AWS information

### About Dockerfile & Dockerfile.dev

1. DOckerfile.dev

   - stands for Dockerfile for development mode.
   - contains baseImage : alpine
   - first copy package.json (for getting only necessarily dependencies)
   - and then npm install (install only necessarily dependencies)
   - copy ./ ./ mean copy other files.
   - after finish work -> compile "npm run start"
   - ENV CHOKIDAR_USEPOLLING=true is only for window os (mac doesn't need it)

2. Dockerfile

   - stands for Dockerfile for production and deployment mode
   - First part(first from) is build stage and second part(second from) is run stage
   - this mode is different from development mode so it needs nginx !!
