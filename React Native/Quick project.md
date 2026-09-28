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
##### Running and viewing in your phone
You need to install the expo go app on your mobile, with the same sdk version that was installed in your project. Here is 55.

To run the program:
```bash
npm start
```
Now in the terminal there are a few things that are need to be discussed.

First you can see a QR code. You can actually scan it using the expo go app you've installed on your mobile app.
Then there are to local links:
```bash
exp://192.168.1.2:8081
http://localhost:8081
```
You can use the first one on the expo go app on your device if the QR code didn't work.
*!Note:* Remember you need to be connected on the same WIFI or any network on both your pc and your mobile.

**First view**
The second link is for viewing in the web. If you check both of them and compare them, there are major differences.
In web version there is a nav bar with some links. In the code you can specify whether you want to display a component on the mobile view or in web.

**Dev tools**
On mobile view there is a settings icon which is the dev tools.
You can reload, view the source code and paths, toggle performance monitor and some other options.

**Android studio**
If running a command in the terminal, you need to have android studio installed and running so you can check it on pc.
Then you need to create a new device in order to generate it's UI on your screen to generate your code in there. This acts as an emulator.

*!Note:* If there was error running your project, run this command:
```bash
npx expo start -c
```
##### Resetting the project
Now that you have created the react native project, you need to remove the default codes in some files.
But the best way is that if you check package.json there's a command that can reset the whole project:
```bash
npm run reset-project
```
It will ask you whether you want to move the existing files to an example directory.
When you do it, run the `npm start` again.

Now you can see that there's a message in the screen which says: `Edit src/app/index.tsx to edit this screen`.

In the path mentioned above, you can change the text inside a tag called `<Text>` to whatever you want.
Now you have an empty project.
##### Some new components in React native
React native is different from react, having pretty much different structure, components and tags, styling and etc.
But the Js logic still remains the same.
In the `index.tsx` file inside the app folder.
You can see there are some components like (StyleSheet, Text, View) that are imported. It's like jsx in react.

Instead of h1s, paragraphs and other HTML tags, you have these components which are for react native. You can read more about the components in [**React native components**](https://reactnative.dev/docs/components-and-apis).

Now if you check `View`, it's one of the most fundamental components for building UIs.
View is a container, in that container you can have flexbox styling, some touch handlings and etc.

So basically every page you create or every screen will be wrapped in a view, and then components within that will be wrapped in a view as well.

In addition to the regular view, you also have **scroll view**. When you go out of the container in regular view, it basically gets cut off. With scroll view you can scroll.

`Text` is another component that we can use a lot, you can consider it as a div, or a paragraph tag.
##### Platform & device checking
In your `src/app/index.tsx`
Replace the existing code with this:
```tsx
import { Text, View, Platform } from "react-native";
  
export default function Index() {
  return (
    <View>
      <Text>This is my app.</Text>
      <Text>Running on: {Platform.OS}</Text>
    </View>
  );
}
```
Now check your mobile. This is used for checking which platform you're currently on.

To check the device info:
```tsx
import { Text, View, Platform } from "react-native";
import * as Device from 'expo-device';
  
export default function HomeScreen() {
  return (
    <View>
      <Text>This is my app.</Text>
      <Text>Running on: {Platform.OS}</Text>
      <Text>Device Model: {Device.modelName}</Text>
      <Text>Device brand: {Device.brand}</Text>
      <Text>OS version {Device.osVersion}</Text>
    </View>
  );
}
```
Now you can see the device info.
##### Inline styling
```tsx
import { Text, View } from "react-native";
  
export default function HomeScreen(){
  return(
    <View
      style={{
        flex:1, justifyContent:'center', alignItems:'center',
        backgroundColor:'cyan'
      }}
    >
      <Text>Hello world</Text>
    </View>
  );
}
```
As you can see, this is inline styling. It's pretty much similar to css styling but of you pay attention, you can see that instead of - between some style attributes like background-color, we have it in camel case form.
*Note:* It's better if you don't style with inline styling. It can make the code look messy.

So we can go with other method.
##### StyleSheet API
```tsx
import {StyleSheet, Text, View } from "react-native";
  
export default function HomeScreen(){
  return(
    <View style={styles.container}>
      <Text style={styles.title}>My app</Text>
      <Text style={styles.date}>Monday, March 16</Text>
    </View>
  );
}
  
const styles=StyleSheet.create({
  container:{
    flex:1,
    backgroundColor:'#1a1a2e',
    paddingTop:60,
    paddingHorizontal:20,
  },
  
  title:{
    fontSize:28,
    fontWeight:'bold',
    color:'#ffffff',
  },
  
  date:{
    fontSize:14,
    color:'#a0a0b0',
    marginTop:4,
    marginBottom:30,
  },
});
```
With this approach, we can create an object which is styles here, and it can have our stylings.
This style is for this page, but we can also have some stylings globally.
##### Changing the header on mobile
There is a header which is `index` in the mobile view, let's remove it.
Check the other file in the app which is `layout`.
```tsx
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return <Stack />;
}
```
This is the code inside the layout file by default.
As you can see, there's the package called stack, this is actually like an stack of screens. Every page you want to show, that page is going on top of the stack.
We just need to keep this code as it is. And we have some options.

To change the header:
```tsx
import { HeaderTitle } from "@react-navigation/elements";
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return <Stack screenOptions={{headerTitle: "My app"}}/>;
}
```
It's good for other pages, since you can put some back buttons and etc. But let's remove it for the home screen:
```tsx
import { HeaderTitle } from "@react-navigation/elements";
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return <Stack screenOptions={{headerShown:false}}/>;
}
```
##### Global styling
Now let's get to global styling, inside the root folder, create a folder called styles, then a file inside it named `global.ts`. Now you can for example use these styles:
```ts
import { Background } from "@react-navigation/elements";
import { StyleSheet } from "react-native";
  
export const colors={
    background:'#1a1a2e',
    header:'#242444',
    surface:'#2a2a4a',
    primary:'#4fc3f7',
    text:'#ffffff',
    textSecondary:'#a0a0b0',
    alert:'#ff5252',
};
  
export const globalStyles=StyleSheet.create({
    container:{
        flex:1,
        backgroundColor:colors.background,
        paddingTop:60,
        paddingHorizontal:20,
    },
  
    title:{
        fontSize:28,
        fontWeight:'bold',
        color:colors.text,
    },
  
    sectionTitle:{
        fontSize:18,
        fontWeight:'600',
        color:colors.textSecondary,
        marginTop:30,
        marginBottom:16,
    },
  
    empty:{
        color:colors.textSecondary,
        fontSize:14,
    },
  
    header:{
        flexDirection:"row",
        justifyContent:'space-between',
        alignItems:'center',
    },
});
```

Now open your main page:
```ts
import {StyleSheet, Text, View } from "react-native";
  
import { globalStyles } from "@/styles/global";
  
export default function HomeScreen(){
  return(
    <View style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <Text style={styles.date}>Monday, March 16</Text>
    </View>
  );
}
  
const styles=StyleSheet.create({
  date:{
    fontSize:14,
    color:'#a0a0b0',
    marginTop:4,
    marginBottom:30,
  },
});
```
##### Home header component
Just like you used to create components folder in React, now create it in `src` folder.

Inside it, create a file named `HomeHeader.tsx`.
```tsx
import { StyleSheet, Text, View } from "react-native";
import { colors, globalStyles } from "@/styles/global";
  
export default function HomeHeader(){
    const currentDate=new Date().toLocaleDateString('en-US',{
        weekday:'long',
        month:'long',
        day:'numeric',
    });
  
    return(
        <View style={globalStyles.header}>
            <Text style={styles.date}>{currentDate}</Text>
        </View>
    );
};
  
const styles=StyleSheet.create({
    date:{
        fontSize:14,
        color:colors.textSecondary,
        marginTop:4,
        marginBottom:30,
    },
});
```

Now you can use it in the main file:
```tsx
import {StyleSheet, Text, View } from "react-native";
import HomeHeader from "@/Components/HomeHeader";
import { globalStyles } from "@/styles/global";
  
export default function HomeScreen(){
  return(
    <View style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <HomeHeader/>
    </View>
  );
};
```
##### Expo router and screens
Now let's add some other pages and routes.
Inside the `app` folder, create a file called: `meals.tsx`.
```tsx
import { globalStyles } from "@/styles/global";
import { ScrollView, Text } from "react-native";
  
export default function MealsScreen(){
    return(
        <ScrollView style={globalStyles.container}>
            <Text style={globalStyles.title}>All meals</Text>
        </ScrollView>
    )
}
```

Now remember we talked about the stack file? Inside it we need to make some differences due to the fact that we have multiple pages in our project.
```tsx
import { HeaderTitle } from "@react-navigation/elements";
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return <Stack screenOptions={{headerShown:false}}>
    <Stack.Screen name="index"/>
    <Stack.Screen name="meals"/>
  </Stack>;
}
```
Remember you need to use the file's name in the stack.
But how do we navigate to our new page?
##### Navigation links
This is how we can go to other pages using the `Link`.
```tsx
import {StyleSheet, Text, View } from "react-native";
import HomeHeader from "@/Components/HomeHeader";
import { globalStyles } from "@/styles/global";
import { Link } from "expo-router";
  
export default function HomeScreen(){
  return(
    <View style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <HomeHeader/>
  
      <Link href='/meals' style={{fontSize:18, color:'#007bff'}}>Go to Meals</Link>
    </View>
  );
};
```
Now you can go to the meals page.
##### Back button & Hide headers
So now let's add a button to go back to the main page.
Open your `layout.tsx` file and write this code:
```tsx
import { colors } from "@/styles/global";
import { HeaderTitle } from "@react-navigation/elements";
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return <Stack screenOptions={{
    headerStyle:{backgroundColor:colors.header},
    headerTintColor:'#fff',
  }}>
    <Stack.Screen name="index" options={{headerShown:false}}/>
    <Stack.Screen name="meals" options={{title:'Meals'}}/>
  </Stack>;
}
```
Now we are only hiding the header on the main page.
Options helps us to customize header here.
##### Add meal screen
Create a file named `add-meal.tsx` in the app folder:
```tsx
import { globalStyles } from "@/styles/global";
import { View, Text } from "react-native";
  
export default function AddMealScreen(){
    return(
        <View style={globalStyles.container}>
            <Text style={globalStyles.title}>Add meal</Text>
        </View>
    )
}
```
Now in layout:
```tsx
import { colors } from "@/styles/global";
import { HeaderTitle } from "@react-navigation/elements";
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return <Stack screenOptions={{
    headerStyle:{backgroundColor:colors.header},
    headerTintColor:'#fff',
  }}>
    <Stack.Screen name="index" options={{headerShown:false, title:"Home"}}/>
    <Stack.Screen name="meals" options={{title:'Meals'}}/>
    <Stack.Screen name="add-meal" options={{title:'Add meals'}}/>
  </Stack>;
}
```

And in index:
```tsx
import {StyleSheet, Text, View } from "react-native";
import HomeHeader from "@/Components/HomeHeader";
import { globalStyles } from "@/styles/global";
import { Link } from "expo-router";
  
export default function HomeScreen(){
  return(
    <View style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <HomeHeader/>
  
      <Link href='/add-meal' style={{fontSize:18, color:'#007bff'}}>Go to add meal</Link>
    </View>
  );
};
```
##### Tabs
Now we need to create tabs, create a folder inside the `app` folder named: `(tabs)` which means this is a group multiple files together. Now move the three page files there: index, add meal, meal.

Now if you check your phone, you can see that the route shows for example if you're on the index:
`(tabs)/index`.

Now we need to create a tabs layout:

First install a package with this command: `npx expo install @expo/vector-icons`

Then Create a file called: `_layout.tsx`
```tsx
import { colors } from "@/styles/global";
import { Ionicons } from '@expo/vector-icons';
import { Tabs } from "expo-router";
  
export default function TabLayout(){
    return(
        <Tabs
            screenOptions={{
                headerShown:false,
                tabBarStyle:{
                    backgroundColor:colors.background,
                    borderTopColor:colors.surface,
                },
                tabBarActiveTintColor:colors.primary,
                tabBarInactiveTintColor:colors.textSecondary,
            }}
        >
            <Tabs.Screen
                name='index'
                options={{
                    title:'Home',
                    tabBarIcon:({color,size})=>(
                        <Ionicons name='home' size={size} color={color}/>
                    ),
                }}
            />
  
            <Tabs.Screen
                name='add-meal'
                options={{
                    title:'Add meal',
                    tabBarIcon:({color,size})=>(
                        <Ionicons name='add-circle' size={size} color={color}/>
                    ),
                }}
            />
  
            <Tabs.Screen
                name='meals'
                options={{
                    title:'All meals',
                    tabBarIcon:({color,size})=>(
                        <Ionicons name='list' size={size} color={color}/>
                    ),
                }}
            />
        </Tabs>
    )
}
```
Now if your check your phone, you can see the tabs bar under the pages.

Now update your root layout file so we only can have one screen:
```tsx
import { colors } from "@/styles/global";
import { HeaderTitle } from "@react-navigation/elements";
import { Stack } from "expo-router";
  
export default function RootLayout() {
  return(
    <Stack screenOptions={{headerShown:false}}>
      <Stack.Screen name="(tabs)"/>
    </Stack>
  );
}
```
This helps us to only have a single screen instead of multiple screens.
##### Card component & grid component
Create a file in components called Card.
```tsx
import { StyleSheet, Text, View } from "react-native";
  
type CardProps={
    label:string;
    value:string;
    goal:string;
    color:string;
};
  
export default function Card({
    label,
    value,
    goal,
    color,
}:CardProps){
    return(
        <View style={[styles.card, {borderLeftColor:color}]}>
            <Text style={styles.label}>{label}</Text>
            <Text style={styles.value}>{value}</Text>
            <Text style={styles.goal}>{goal}</Text>
        </View>
    )
};
  
const styles=StyleSheet.create({
    card:{
        backgroundColor:'#16213e',
        borderRadius:12,
        padding:16,
        width:"47%",
        borderLeftWidth:4,
    },
  
    label:{
        fontSize:14,
        color:"#a0a0b0",
    },
  
    value:{
        fontSize:28,
        fontWeight:"bold",
        color:"#ffffff",
        marginTop:4,
    },
  
    goal:{
        fontSize:14,
        color:"#a0a0b0",
        marginTop:2,
    },
});
```

Now another one named `CardGrid`
```tsx
import { StyleSheet, View } from "react-native";
import Card from "./Card";
  
export default function CardGrid(){
    return(
        <View style={styles.grid}>
            <Card label="Calories" value="0" goal="2000" color="#ff6b6b"/>
            <Card label="Protein" value="0g" goal="150g" color="#4ecdc4"/>
            <Card label="Carbs" value="0g" goal="250g" color="#ffd93d"/>
            <Card label="Fat" value="0g" goal="65g" color="#6bcb77"/>
        </View>
    )
};
  
const styles=StyleSheet.create({
    grid:{
        flexDirection:'row',
        flexWrap:'wrap',
        gap:12,
    },
});
```
Now let's add it into home screen. In tabs folder inside the index file:
```tsx
import {StyleSheet, Text, ScrollView } from "react-native";
import HomeHeader from "@/Components/HomeHeader";
import { globalStyles } from "@/styles/global";
import { Link } from "expo-router";
import CardGrid from "@/Components/CardGrid";
  
export default function HomeScreen(){
  return(
    <ScrollView style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <HomeHeader/>
      <CardGrid/>
    </ScrollView>
  );
};
```
##### Meal item & Recent meals components
In your components folder, create a file named:`MealItem.tsx`
```tsx
import { StyleSheet, Text, View } from "react-native";
  
type MealItemProps={
    name:string;
    calories:number;
    protein:number;
    carbs:number;
    fat:number;
};
  
export default function MealItem({
    name,
    calories,
    protein,
    carbs,
    fat,
}:MealItemProps){
    return(
        <View style={styles.container}>
            <Text style={styles.name}>{name}</Text>
            <Text style={styles.macros}>
                {calories} cal . {protein}g P . {carbs}g C . {fat}g F
            </Text>
        </View>
    )
}
  
const styles=StyleSheet.create({
    container:{
        backgroundColor:'#16213e',
        borderRadius:10,
        padding:16,
        marginBottom:10,
    },
  
    name:{
        fontSize:16,
        fontWeight:'600',
        color:"#ffffff",
    },
  
    macros:{
        fontSize:13,
        color:'#a0a0b0',
        marginTop:4,
    },
});
```

And also another component named: `RecentMeals`:
```tsx
import { StyleSheet, Text, View } from "react-native";
import { globalStyles } from "@/styles/global";
import MealItem from "./MealItem";
  
export default function RecentMeals(){
    return(
        <View style={{marginTop:30}}>
            <Text style={globalStyles.sectionTitle}>Recent meals</Text>
  
            <MealItem
                name='Chicken & rice'
                calories={540}
                protein={45}
                carbs={50}
                fat={12}
            />
  
            <MealItem
                name='Protein shake'
                calories={280}
                protein={30}
                carbs={20}
                fat={0}
            />
  
            <MealItem
                name='Salmon salad'
                calories={430}
                protein={35}
                carbs={10}
                fat={25}
            />
        </View>
    );
}
```
Now add it into the homescreen:
```tsx
import {StyleSheet, Text, ScrollView } from "react-native";
import HomeHeader from "@/Components/HomeHeader";
import { globalStyles } from "@/styles/global";
import { Link } from "expo-router";
import CardGrid from "@/Components/CardGrid";
import RecentMeals from "@/Components/RecentMeals";
  
export default function HomeScreen(){
  return(
    <ScrollView style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <HomeHeader/>
      <CardGrid/>
      <RecentMeals/>
    </ScrollView>
  );
};
```
Since the data above as you see is hard coded, let's create an add meal form and then storage after it.
##### Add meal form
Remember that we've created an add meal page before, now replace it with this code:
```tsx
import { colors, globalStyles } from "@/styles/global";
import { useState } from "react";
import { StyleSheet, Text, TextInput, TouchableOpacity, View } from "react-native";
  
export default function AddMealScreen(){
    const [name, setName]=useState('');
    const [calories, setCalories]=useState('');
    const [protein, setProtein]=useState('');
    const [carbs, setCarbs]=useState('');
    const [fat, setFat]=useState('');
  
    const handleAddMeal=()=>{
        console.log({ name, calories, protein, carbs, fat });
    };
  
    return(
        <View style={globalStyles.container}>
            <Text style={globalStyles.title}>Add meals</Text>

            <TextInput
                style={styles.input}
                placeholder="Meal name"
                placeholderTextColor={colors.textSecondary}
                value={name}
                onChangeText={setName}
            />
  
            <TextInput
                style={styles.input}
                placeholder="Calories"
                placeholderTextColor={colors.textSecondary}
                value={calories}
                onChangeText={setCalories}
            />
            <View style={styles.row}>
                <TextInput
                    style={[styles.input, styles.rowInput]}
                    placeholder="Protein (g)"
                    placeholderTextColor={colors.textSecondary}
                    keyboardType="numeric"
                    value={protein}
                    onChangeText={setProtein}
                />
  
                <TextInput
                    style={[styles.input, styles.rowInput]}
                    placeholder="Carbs (g)"
                    placeholderTextColor={colors.textSecondary}
                    keyboardType="numeric"
                    value={carbs}
                    onChangeText={setCarbs}
                />
  
                <TextInput
                    style={[styles.input, styles.rowInput]}
                    placeholder="Fat (g)"
                    placeholderTextColor={colors.textSecondary}
                    keyboardType="numeric"
                    value={fat}
                    onChangeText={setFat}
                />
            </View>
  
            <TouchableOpacity style={styles.button} onPress={handleAddMeal}>
                <Text style={styles.buttonText}>Add meal</Text>
            </TouchableOpacity>
        </View>
    );
}
  
const styles=StyleSheet.create({
    input:{
        backgroundColor:colors.surface,
        color:colors.text,
        padding:16,
        borderRadius:10,
        fontSize:16,
        marginTop:16,
    },
  
    row:{
        flexDirection:'row',
        gap:10,
    },
  
    rowInput:{
        flex:1,
    },
  
    button:{
        backgroundColor:colors.background,
        padding:16,
        borderRadius:10,
        alignItems:"center",
        marginTop:24,
    },
  
    buttonText:{
        color:colors.background,
        fontSize:16,
        fontWeight:'bold',
    },
});
```

Now we're ready for the async storage.
##### Async storage
When you build a mobile app. you often need to store data. This maybe through an API or locally on the device. For local storage in React native, a common solution is to use `AsyncStorage` which is a simple **key value storage system** that allows you to persist data across app launches.

Install the package using the command below:
```bash
npx expo install @react-native-async-storage/async-storage
```

**Quick AsyncStorage Example (Don't add to project)**
```tsx
import AsyncStorage from '@react-native-async-storage/async-storage';

// To save data
const saveData = async (key: string, value: any) => {
  try {
    const jsonValue = JSON.stringify(value);
    await AsyncStorage.setItem(key, jsonValue);
  } catch (e) {
    console.error('Error saving data', e);
  }
};

// To retrieve data
const getData = async (key: string) => {
  try {
    const jsonValue = await AsyncStorage.getItem(key);
    return jsonValue != null ? JSON.parse(jsonValue) : null;
  } catch (e) {
    console.error('Error retrieving data', e);
  }
};
```
As you can see, it is very similar to using `localStorage` in a web app, but with async/await syntax since it is asynchronous. You can use these functions to save and retrieve datas in your app.

This will save actual JSON file.

Now to use this, let's create a storage handler.
##### Storage handler
Create a folder called storage in the src folder. Create a file inside it and for example name it `meals.tsx`.
```ts
import AsyncStorage from '@react-native-async-storage/async-storage';
  
export type Meal={
    id:string;
    name:string;
    calories:number;
    protein:number;
    carbs:number;
    fat:number;
    createdAt:string;
};
  
const MEALS_KEY='meals';
  
export const getMeals=async():Promise<Meal[]> => {
    const data=await AsyncStorage.getItem(MEALS_KEY);
    return data ? JSON.parse(data) : [];
};
  
export const addMeal=async(meal: Omit<Meal, 'id' | 'createdAt'>,):Promise<Meal> => {
    const meals=await getMeals();
    const newMeal:Meal={
        ...meal,
        id: Date.now().toString(),
        createdAt: new Date().toISOString(),
    };
  
    await AsyncStorage.setItem(MEALS_KEY, JSON.stringify([newMeal, ...meals]));
    return newMeal;
}
```
This code defines a `Meal` type and two functions: `getMeals` to retrieve the list of meals from storage, and `addMeal` to add a new meal to the storage. The meals are stored as an array in `AsyncStorage` under the key `meals`. Each meal has a unique ID generated from the current timestamp and a createdAt timestamp.
##### Connecting the form to storage
Now let's update the add meal form to use the `addMeal` function from our storage handler to save meals to `AsyncStorage`. Open `src/app/(tabs)/add-meal.tsx` and update the `handleAddMeal` function to the following:
```tsx
import { useState } from 'react';
import {
  StyleSheet,
  Text,
  TextInput,
  TouchableOpacity,
  View,
  Alert,
} from 'react-native';
import { colors, globalStyles } from '@/styles/global';
  
import { addMeal } from '@/Storage/meals';
import { router } from 'expo-router';
  
export default function AddMealScreen() {
  const [name, setName] = useState('');
  const [calories, setCalories] = useState('');
  const [protein, setProtein] = useState('');
  const [carbs, setCarbs] = useState('');
  const [fat, setFat] = useState('');
  
  const handleAddMeal = async () => {
    if(!name || !calories){
      Alert.alert("Error, please enter a meal name and calories");
      return;
    }
  
    await addMeal({
      name,
      calories:Number(calories),
      protein:Number(protein) || 0,
      carbs:Number(carbs) || 0,
      fat:Number(fat) || 0,
    });
  
    setName('');
    setCalories('');
    setProtein('');
    setCarbs('');
    setFat('');
  
    Alert.alert('Success', 'Meal added successfully');
  
    router.push('/');
  };
  
  return (
    <View style={globalStyles.container}>
      <Text style={globalStyles.title}>Add Meal</Text>
  
      <TextInput
        style={styles.input}
        placeholder='Meal name'
        placeholderTextColor={colors.textSecondary}
        value={name}
        onChangeText={setName}
      />
  
      <TextInput
        style={styles.input}
        placeholder='Calories'
        placeholderTextColor={colors.textSecondary}
        keyboardType='numeric'
        value={calories}
        onChangeText={setCalories}
      />
  
      <View style={styles.row}>
        <TextInput
          style={[styles.input, styles.rowInput]}
          placeholder='Protein (g)'
          placeholderTextColor={colors.textSecondary}
          keyboardType='numeric'
          value={protein}
          onChangeText={setProtein}
        />
        <TextInput
          style={[styles.input, styles.rowInput]}
          placeholder='Carbs (g)'
          placeholderTextColor={colors.textSecondary}
          keyboardType='numeric'
          value={carbs}
          onChangeText={setCarbs}
        />
        <TextInput
          style={[styles.input, styles.rowInput]}
          placeholder='Fat (g)'
          placeholderTextColor={colors.textSecondary}
          keyboardType='numeric'
          value={fat}
          onChangeText={setFat}
        />
      </View>
  
      <TouchableOpacity style={styles.button} onPress={handleAddMeal}>
        <Text style={styles.buttonText}>Add Meal</Text>
      </TouchableOpacity>
    </View>
  );
}
  
const styles = StyleSheet.create({
  input: {
    backgroundColor: colors.surface,
    color: colors.text,
    padding: 16,
    borderRadius: 10,
    fontSize: 16,
    marginTop: 16,
  },
  row: {
    flexDirection: 'row',
    gap: 10,
  },
  rowInput: {
    flex: 1,
  },
  button: {
    backgroundColor: colors.primary,
    padding: 16,
    borderRadius: 10,
    alignItems: 'center',
    marginTop: 24,
  },
  buttonText: {
    color: colors.background,
    fontSize: 16,
    fontWeight: 'bold',
  },
});
```
##### Add recent meals to home screen
Open `src/app/(tabs)/index.tsx` and import the `getMeals` function from the storage handler and use it to retrieve the meals from storage. Update the file to the following:
```tsx
import { getMeals, Meal } from '@/Storage/meals';
import { globalStyles } from '@/styles/global';
import { useFocusEffect } from 'expo-router';
import { useCallback, useState } from 'react';
import { ScrollView, Text } from 'react-native';
  
import HomeHeader from "@/Components/HomeHeader";
import CardGrid from "@/Components/CardGrid";
import RecentMeals from "@/Components/RecentMeals";
  
export default function HomeScreen(){
  const [meals, setMeals]=useState<Meal[]>([]);
  
  const loadMeals=async()=>{
    const data=await getMeals();
    setMeals(data);
    console.log('Loaded meals:', data);
  };
  
  useFocusEffect(
    useCallback(()=>{
      loadMeals();
    },[]),
  );
  
  return(
    <ScrollView style={globalStyles.container}>
      <Text style={globalStyles.title}>My app</Text>
      <HomeHeader/>
      <CardGrid/>
      <RecentMeals meals={meals}/>
    </ScrollView>
  );
};
```
You will not see anything change in the UI yet because we haven't updated the `RecentMeals` component, but if you check the console logs, you should see the loaded meals being logged whenever you navigate back to the home screen or reload the app.

We use the `useFocusEffect` hook from `expo-router` to load the meals whenever the home screen comes into focus. This ensures that we always have the latest meals from storage whenever we view the home screen. If we use a regular `useEffect` with an empty dependency array, it would only load the meals once when the component mounts and would not update when we add new meals and navigate back to the home screen.
##### Update recent meals to use Storage handler
Now we need to update the recent pages:
```tsx
import { StyleSheet, Text, View } from "react-native";
import { Meal } from "@/Storage/meals";
import { globalStyles } from "@/styles/global";
import MealItem from "./MealItem";
  
type RecentMealsProps={
    meals:Meal[];
}
  
export default function RecentMeals({ meals }:RecentMealsProps){
    return (
    <View style={{ marginTop: 30 }}>
      <Text style={globalStyles.sectionTitle}>Recent Meals</Text>
      {meals.length === 0 ? (
        <Text style={globalStyles.empty}>No meals logged yet.</Text>
      ) : (
        meals
          .slice(0, 5)
          .map((meal) => (
            <MealItem
              key={meal.id}
              name={meal.name}
              calories={meal.calories}
              protein={meal.protein}
              carbs={meal.carbs}
              fat={meal.fat}
            />
          ))
      )}
    </View>
  );
}
```
##### Upgrade card grids to calculate totals
Now let's update the `CardGrid` component to calculate the total calories, protein, carbs, and fat from the meals and display them in the macro cards.

First, we need to pass the meals as a prop to the `CardGrid` component. Open `src/app/(tabs)/index.tsx` and update the `CardGrid` component to the following:
```tsx
<CardGrid meals={meals} />
```

Now Open `src/components/MacroGrid.tsx` and update to the following:
```tsx
import { StyleSheet, View } from "react-native";
import Card from "./Card";
import { Meal } from "@/Storage/meals";
  
type CardGridProps={
    meals:Meal[];
};
  
export default function CardGrid({meals}: CardGridProps){
    const totals=meals.reduce((acc, meal)=>({
        calories:acc.calories+meal.calories,
        protein:acc.protein+meal.protein,
        carbs:acc.carbs+meal.carbs,
        fat:acc.fat+meal.fat,
    }),
        { calories:0, protein:0, carbs:0, fat:0 },
    );
  
    return(
        <View style={styles.grid}>
            <Card label="Calories" value={`${totals.calories}`} goal="2000" color="#ff6b6b"/>
            <Card label="Protein" value={`${totals.protein}`} goal="150g" color="#4ecdc4"/>
            <Card label="Carbs" value={`${totals.carbs}`} goal="250g" color="#ffd93d"/>
            <Card label="Fat" value={`${totals.fat}`} goal="65g" color="#6bcb77"/>
        </View>
    );
}
  
const styles=StyleSheet.create({
    grid:{
        flexDirection:'row',
        flexWrap:'wrap',
        gap:12,
    },
});
```
##### Delete meals functionally
Let's add the ability to delete meals from storage. First, we need to add a delete function to our storage handler. Open `src/storage/meals.ts` and add the following function:
```tsx
export const deleteMeal=async(id:string): Promise<void> => {
    const meals=await getMeals();
    const filtered=meals.filter((meal)=> meal.id !== id);
    await AsyncStorage.setItem(MEALS_KEY, JSON.stringify(filtered));
};
```
This function takes in the ID of the meal to delete, retrieves the current meals from storage, filters out the meal with the matching ID, and then saves the updated list back to storage.
##### Update meal item to delete meals
Now let's update the `MealItem` component to include a delete button that calls the `deleteMeal` function. Open `src/components/MealItem.tsx` and update to the following:
```tsx
import { Alert, StyleSheet, Text, View, TouchableOpacity } from "react-native";
import { deleteMeal } from "@/Storage/meals";
import { colors } from "@/styles/global";

type MealItemProps={
    name:string;
    calories:number;
    protein:number;
    carbs:number;
    fat:number;
    id:string;
    onDelete:()=>void;
};
  
export default function MealItem({
    id,
    name,
    calories,
    protein,
    carbs,
    fat,
    onDelete,
}:MealItemProps){
    const handleLongPress=()=>{
        Alert.alert('Delete Meal', `Are you sure you want to delete "${name}"?`,[
            {text:'Cancel', style:'cancel'},
            {
                text:'Delete',
                style:'destructive',
                onPress:async()=>{
                    await deleteMeal(id);
                    onDelete;
                }
            }
        ])
    }
    return(
        <TouchableOpacity style={styles.container}>
            <Text style={styles.name}>{name}</Text>
            <Text style={styles.macros}>
                {calories} cal . {protein}g P . {carbs}g C . {fat}g F
            </Text>
        </TouchableOpacity>
    )
}
  
const styles = StyleSheet.create({
  container: {
    backgroundColor: colors.surface,
    borderRadius: 10,
    padding: 16,
    marginBottom: 10,
  },
  name: {
    fontSize: 16,
    fontWeight: '600',
    color: colors.text,
  },
  macros: {
    fontSize: 13,
    color: colors.textSecondary,
    marginTop: 4,
  },
});
```
We added an `onDelete` prop to the `MealItem` component, which is a function that will be called after a meal is deleted. We also added a long press handler that shows an alert asking the user to confirm the deletion. If the user confirms, it calls the `deleteMeal` function from the storage handler and then calls the `onDelete` callback to refresh the meals list.
##### Update recent meals to pass the Delete callback
Finally, we need to pass the `loadMeals` function as the `onDelete` callback to the `MealItem` components in the `RecentMeals` component. Open `src/components/RecentMeals.tsx` and update to the following:
```tsx
import { StyleSheet, Text, View } from 'react-native';
import { Meal } from '@/Storage/meals';
import MealItem from './MealItem';
  
type RecentMealsProps = {
  meals: Meal[];
  onDelete: () => void;
};
  
export default function RecentMeals({ meals, onDelete }: RecentMealsProps) {
  return (
    <View style={{ marginTop: 30 }}>
      <Text style={styles.sectionTitle}>Recent Meals</Text>
      {meals.length === 0 ? (
        <Text style={styles.empty}>No meals logged yet.</Text>
      ) : (
        meals
          .slice(0, 5)
          .map((meal) => (
            <MealItem
              key={meal.id}
              id={meal.id}
              name={meal.name}
              calories={meal.calories}
              protein={meal.protein}
              carbs={meal.carbs}
              fat={meal.fat}
              onDelete={onDelete}
            />
          ))
      )}
    </View>
  );
}
  
const styles = StyleSheet.create({
  sectionTitle: {
    fontSize: 18,
    fontWeight: '600',
    color: '#ffffff',
    marginBottom: 16,
  },
  empty: {
    color: '#a0a0b0',
    fontSize: 14,
  },
});
```

We also need to pass the `loadMeals` function as the `onDelete` callback to the `RecentMeals` component on the home screen. Open `src/app/(tabs)/index.tsx` and add it as a prop to the `RecentMeals` component:
```tsx
<RecentMeals meals={meals} onDelete={loadMeals} />
```
