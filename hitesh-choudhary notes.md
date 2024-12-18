# react-native file structure
- `_tests` folder: it contains files for testing of react-native apps
- `.bundle` folder: configuration files that need not be cared about(dont touch these)
- `android` & `ios` folders: in react-native world, code is written once in the `app.js` or `app.tsx` file and then subsequently the code is moved either the android world, or the ios world.
	- `android` folder contains `build.gradle`, which contains stuff like `targetSdkVersion` and `minSdkVersion`, and `dependencies`.
- `node_modules` folder: contains the node dependencies
- `.eslintrc.js`: contains linting configuration
- `.gitignore`: we don't want some files to pushed when using git, and that is when this file comes handy
- `.prettierrc.js`: contains developer configuration, just for the ease of developers, doesn't matter when the code goes into production
- `.watchmanconfig`: contains configuration for watchman(https://facebook.github.io/watchman/).
- `app.json`: a major config file, the application takes it's name from this file
- `App.tsx`: the main file which contains all the application code and gets rendered
- `babel.config.js`: bundler file which combines all of the files in the project for it to work properly as an application in the browser or on a mobile phone. here, react-native uses babel configuration, within which `metro` configuration is used
-  `Gemfile`: ruby-based file for ios development, not to be touched
- `index.js`: out of the box, the application doesn't know which file to load up, so initially, the metro builder opens up this file(`index.js`). 
	- ![](attachments/Pasted%20image%2020241217161825.png) Here, `AppRegistry` is responsible for the magic behind the react-native to android or ios development
- `metro.config.js`: config file for the Metro bundler
- `package-lock.json`: contains version of all the node packages
- `package.json`: contains node package configuration
- `tsconfig.json`: typescript configuration file

# 