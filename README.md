# Create Looker CusViz Development Environment

1. install [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
2. in your terminal, `cd path-to-your-project-folder` then `npm init -y`
    1. it’ll auto-generate “package.json” in root folder
3. install a bunch of packages
    1. it’ll auto-generate a folder “node_modules” and a file “package-lock.json” in root folder once you start install packages

```sql
npm install webpack --save-dev
npm install webpack-cli --save-dev
npm install webpack-dev-server --save-dev
npm install typescript --save-dev
npm install ts-loader --save-dev
npm install style-loader --save-dev
npm install css-loader --save-dev
npm install sass-loader --save-dev
npm install sass --save-dev
npm install terser-webpack-plugin --save-dev
npm install ts-node --save-dev
npm install d3 --save
```

4. create folder structure as below and create a few files in it
    - my-project
        - src
            - common
                - types.ts
                - utils.ts
            - visualizations
                - myTemplace.ts
    - package.json
    - tsconfig.json
    - webpack.config.js
5. add two lines in package.json in “script” section
    
    "build": "webpack”
    
    "start:dev": "webpack-dev-server"
    
6. run “npm run build” to create output .js file in ./dist
7. run “npm run start:dev” to start local server
    1. if you set up successfully, once you run it, you should see a local server webpage pop up
    2. to test it, you can do [localhost:3443/myTemplate.js](http://localhost:3443/myTemplate.js) to see the generated js script
8. add the local file reference to Looker
    1. Navigate to the Admin page in Looker
    2. Select Visualizations from the left nav
    3. Select the Add visualization button
    4. Fill out the form
    
    ExampleID: my-custom-viz-dev Label: My Custom Visualization - DevelopmentMain: [https://localhost:3443/myTemplate.js](https://localhost:3443/myCustomViz.js)
    
    5. Select Save
    6. Create or go to an Explore and you should see the custom visualization in the menu. select it.
    7. Add some data so your explore has some data
    8. Start your local webserver by running the `npm script start:dev`
