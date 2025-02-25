# react-native-create-library
Tool to create a React Native library with a single command.

![](https://github.com/frostney/react-native-create-library/blob/master/docs/usage.gif)

### Why might you need this?
If you are looking to create a native module for React Native, you need some native code for each platform you want to support and then some JavaScript code to bind it all together. Setting this up by yourself can be time-consuming.

This is where this tool comes in. It creates a boilerplate with all current best practices in mind.
Why not use `react-native new-library`? Unfortunately that command doesn't create an up-to-date library, requires an already initialized React Native project and only sets up the iOS side of things.

Caution: This only creates native modules without a view component.

### Alternatives
[react-native-create-bridge](https://github.com/peggyrayzis/react-native-create-bridge)

## Installation
Requirements: Node 6.0+
```
$ npm install -g react-native-create-library
```

## Command-line usage

Navigate into an empty directory to execute the command.
```
$ react-native-create-library MyFancyLibrary
```

This will create the folder `MyFancyLibrary` in which the library will be created in.

Now install dependencies by running this command in the newly created library.
```
$ npm install
```

```
Usage: react-native-create-library [options] <name>

Options:

  -h, --help                                output usage information
  -V, --version                             output the version number
  -p, --prefix <prefix>                     The prefix for the library (Default: `RN`)
  --module-prefix <modulePrefix>            The module prefix for the library (Default: `react-native`)
  --package-identifier <packageIdentifier>  (Android only!) The package name for the Android module (Default: `com.reactlibrary`)
  --namespace <namespace>                   (Windows only!) The namespace for the Windows module
   (Default: The name as PascalCase)
  --platforms <platforms>                   Platforms the library will be created for. (comma separated; default: `ios,android,windows`)
  --github-account <github_account>         The github account where the library is hosted (Default: `github_account`)
  --author-name <name>                      The author's name (Default: `Your Name`)
  --author-email <email>                    The author's email (Default: `yourname@email.com`)
  --license <license>                       The license type of this library (Default: `Apache-2.0`)
  --generate-example <shouldGenerate>       Will generate a RN example project and link the new library to it (Default: `false`)

例如：react-native-create-library --package-identifier cn.cnlee.commons --platforms android,ios --github-account lijian0103 --author-name lijian --author-email lijian0103@hotmail.com --license MIT

```

## Programmatic usage
```javascript
const createLibrary = require('react-native-create-library');

createLibrary({
  name: 'MyFancyLibrary'
}).then(() => {
  console.log('Oh yay! My library has been created!');
})
```

#### Options
```javascript
{
  name: String, /* The name of the library (Default: Library) */
  prefix: String, /* The prefix for the library (Default: RN) */
  modulePrefix: String, /* The module prefix for the library (Default: react-native) */
  platforms: Array, /* Platforms the library will be created for. (Default: ['ios', 'android', 'windows']) */
  packageIdentifier: String, /* (Android only!) The package name for the Android module (Default: com.reactlibrary) */
  namespace: String, /* (Windows only!) The namespace for the Windows module (Default: The package identifier as PascalCase, which is `Com.Reactlibrary`) */
  githubAccount: String, /* The github account where the library is hosted (Default: `github_account`) */
  authorName: String, /* The author's name (Default: `Your Name`) */
  authorEmail: String, /* The author's email (Default: `yourname@email.com`) */ 
  license: String, /* The license type of this library (Default: `Apache-2.0`) */
  generateExample: Boolean, /* Will generate a RN example project and link the new library to it (Default: `false`) */
}
```

## Acknowledgements
`react-native-share` (https://github.com/EstebanFuentealba/react-native-share) has been a great source of inspiration for this project.

## License
MIT
