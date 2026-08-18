React native is mostly used for creating and designing mobile apps.

##### Steps to create a project
In order to create a react native project, we need to create an account on [Expo](https://expo.dev/).
Once you created your account, go for the **New project** button.
There will be suggestions to build your project.
But use these instead:
```bash
npm install --global eas-cli
npx create-expo-app@latest --template default@sdk-55
cd reactnativetest
eas init --id a63f9f00-b4c8-4611-9bff-1e8aed625543
```
The `reactnativetest` you see is just an example name.
The first command is for installing the eas cli globally on your pc.
The second one builds the project.
Use the cd command to move in to your project.
The 4th command is for linking the project to the expo project you just created. The id above will be different. 