# Exercice 1 : Création d'une application à deux écrans avec React Native

Dans cet exercice, nous allons créer une application simple avec deux écrans en utilisant React Native et la bibliothèque React Navigation. Nous allons construire cette application étape par étape, en suivant les instructions ci-dessous.

Démonstration disponible sur ma chaîne YouTube: https://youtube.com/@codeurlibre

et article sur mon blog: https://codeurlibre.systeme.io/dbuter-avec-react-native--cration-dune-application-simple-avec-expo-et-react-navigation

**Objectifs de l'exercice :**

1. Comprendre les principes fondamentaux de React Native.
2. Apprendre à naviguer entre différents écrans avec React Navigation.
3. Pratiquer la construction d'une application React Native simple.

**Instructions :**

1. **Initialisation du projet :** Commencez par initialiser un nouveau projet React Native avec Expo en utilisant la commande `expo init nom_du_projet`.

2. **Installation de React Navigation :** Installez ensuite la bibliothèque React Navigation en utilisant la commande `npm install @react-navigation/native @react-navigation/stack`.

3. **Création des écrans :** Créez deux nouveaux fichiers dans le dossier `screens`, `HomeScreen.js` et `ProfileScreen.js`. Vous pouvez les remplir avec le code fourni.

4. **Configuration de la navigation :** Créez une pile de navigation dans votre fichier `App.js` et ajoutez vos deux écrans à cette pile.

5. **Test de l'application :** Exécutez votre application avec la commande `npm start` ou `expo start`, et testez la navigation entre vos deux écrans.

**App.js :**

```js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';

import HomeScreen from './screens/HomeScreen';
import ProfileScreen from './screens/ProfileScreen';

const Tab = createBottomTabNavigator();

export default function App() {
    return (
        <NavigationContainer>
            <Tab.Navigator>
                <Tab.Screen name="Home" component={HomeScreen} />
                <Tab.Screen name="Profile" component={ProfileScreen} />
            </Tab.Navigator>
        </NavigationContainer>
    );
}
```

**HomeScreen.js :**

```js
import React from 'react';
import { View, Text, Image, StyleSheet } from 'react-native';

const HomeScreen = () => {
    return (
        <View style={styles.container}>
            <Text style={styles.title}>Bienvenue à la maison !</Text>
            <Image
                style={styles.image}
                source={require('../assets/home.png')}
            />
            <Text style={styles.text}>Ceci est une démonstration de React Native.</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        alignItems: 'center',
        justifyContent: 'center',
        backgroundColor: '#F5FCFF',
    },
    title: {
        fontSize: 20,
        textAlign: 'center',
        margin: 10,
    },
    image: {
        width: 200,
        height: 200,
        margin: 15,
    },
    text: {
        textAlign: 'center',
        color: '#333333',
        marginBottom: 5,
    },
});

export default ProfileScreen;
```

**ProfileScreen.js :**

```js
import React from 'react';
import { View, Text, Image, StyleSheet } from 'react-native';

const ProfileScreen = () => {
    return (
        <View style={styles.container}>
            <Text style={styles.title}>Mon profil</Text>
            <Image
                style={styles.image}
                source={require('../assets/profil.png')}
            />
            <Text style={styles.text}>Ceci est mon profil.</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        alignItems: 'center',
        justifyContent: 'center',
        backgroundColor: '#F5FCFF',
    },
    title: {
        fontSize: 20,
        textAlign: 'center',
        margin: 10,
    },
    image: {
        width: 200,
        height: 200,
        margin: 15,
    },
    text: {
        textAlign: 'center',
        color: '#333333',
        marginBottom: 5,
    },
});

export default ProfileScreen;
```