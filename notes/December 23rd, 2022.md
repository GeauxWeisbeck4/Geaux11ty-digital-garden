- # Friday 12/23/22
    - I need to figure out how to make some money bad this weekend so I can be sure and pay rent - if anyone h`as any ideas let me know :).
- 
- # To Do Today
    - {{[[DONE]]}} [[SSG Challenge]]
        - {{[[DONE]]}} [[Fresh]]
    - {{[[DONE]]}} [[Framework Challenge]]
        - {{[[DONE]]}} [[Ember.js]]
    - {{[[TODO]]}} [[CMS Challenge]]
    - {{[[TODO]]}} Record for [[Mean Stack Developer Paid Newsletter]]
    - {{[[TODO]]}} Write [[MEAN Stack Developer]]
    - {{[[DONE]]}} Blog Post - [[Content Calendar]]
        - {{[[DONE]]}} [[Medium]]
    - {{[[DONE]]}} [[MEAN Notes]]
    - {{[[TODO]]}} [[Roadmap.sh]]
    - {{[[DONE]]}} Clean up Graph and combine with Logseq for [[Digital Garden]]
- # Resources, Readings, and Links
    - https://www.testerup.com/
    - https://iexcloud.io/
    - [Vanilla JS (vanilla-js.com)](http://vanilla-js.com/)
    - http://www.troubleshooters.com/
- # My Dev Setup
    - I am going to create my "Official Dev Environment" for productive coding.
    - Abstract:
        - I tend to get really distracted every time I sit down to code or learn about something in coding. There are so many frameworks to check out, new tools, and the internet is so vast... I get stuck and miss out on hours of coding time where I should be focused and doing my job.
        - To change this, I am going to develop my own setup to minimize distractions, enhance focus, boost efficiency, and promote creativity. I need to have only what I need to have open on my main computer screen and all other things put away. 
    -  Draft:
        - I will need to only leave a few windows open that are ok when developing. They are:
            - Taskade
            - Notion/Roam/Logseq
            - Stackblitz/Codepen/Replit/Div Riots
            - Figma/Penpot etc.
            - IDE
            - 
- #huskers
    - Forestry.io Just announced their end of life date: March 22, 2023

__The full announcement is on their [Slack](https://forestry-community.slack.com/archives/C2R43R7SB/p1671733908873459) (open to join). Here's the skinny:

* End of life is March 22nd, 2023
* Everything is switching to [TinaCMS](https://tina.io/)
* They provided docs for [migration](https://tina.io/docs/forestry/overview/) and how it will [impact various frameworks](https://tina.io/docs/forestry/missing-forestry-features/) 

I haven't used Tina yet, but hopefully it's as easy to configure and user-friendly as [Forestry.io](https://Forestry.io)

- by eddydio on [r/JAMstack](https://www.reddit.com/r/JAMstack/comments/zsttcj/forestryio_just_announced_their_end_of_life_date/)__ (4 upvotes) #huskers
    - Video Tutorial &gt; Customizable React Navbar With Built-In Routing Support

__- by Superflows-Dev on [r/react](https://www.reddit.com/r/react/comments/zt5exn/video_tutorial_customizable_react_navbar_with/)__ (1 upvotes) #huskers
    - This is how to disable automatic 'user agent stylesheet' styles on MUI textfield component.

__Posting this to hopefully spare others the pain that I went through to disable Chrome's automatic styling of inputs when auto-filling.

To clarify, when Chrome auto-fills MUI textfields, it also forces the background color to a horrible off-white color, which makes any auto-filled text invisible if your app is dark theme and uses white text in inputs.

To get around this, I eventually intercepted the component in my app, created a new styled version using MUI's `styled` function, and set the `-webkit-box-shadow` property to `0 0 0 100px #yourHexColor` and an `!important` tag to enforce it.

Like so: 

    const StyledTextField = styled(TextField)(({ theme }) =&gt; ({
      input: {
        '-webkit-box-shadow': `0 0 0 100px ${theme.palette.background.default} inset !important`,
      },
    }));

If this spares even one person the headaches I went through, it will be worth it.

- by BavarianDuck89 on [r/react](https://www.reddit.com/r/react/comments/ztkjlw/this_is_how_to_disable_automatic_user_agent/)__ (5 upvotes) #huskers
    - Firebase: need to provide options when not being deployed via hosting source (app/no-options)

__import React from 'react';

import {  getAuth } from 'firebase/auth';

import { GoogleAuthProvider } from 'firebase/auth';



import {

  StyleSheet,

  Text,

  View,

  ScrollView,

  TouchableOpacity,

  AsyncStorage

} from 'react-native';



import Header from './src/view/Header';

import Footer from './src/view/Footer';

import Body from './src/view/body';


const auth =  getAuth()

export {auth};



export default function App(){

  

  const [user] = useAuthState(auth);


    return (

      &lt;View style={styles.container}&gt;

        

        &lt;Header/&gt;

        

        &lt;section&gt;

          {user ? &lt;HomePage /&gt; : &lt;SignIn /&gt;}

        &lt;/section&gt;


      &lt;/View&gt;

    );

  



}

function SignIn() {


  const signInWithGoogle = () =&gt; {

    const provider = new firebase.auth.GoogleAuthProvider();

    auth.signInWithPopup(provider);

  }


  return (

    

      &lt;button className="sign-in" onClick={signInWithGoogle}&gt;Sign in with Google&lt;/button&gt;

     

   

  )


}

- by cheesyboi12345 on [r/react](https://www.reddit.com/r/react/comments/zt59uo/firebase_need_to_provide_options_when_not_being/)__ (2 upvotes) #huskers
    - Pot Roast DL interview

__- by xdeathxcomoanyx on [r/Huskers](https://www.reddit.com/r/Huskers/comments/zt09f4/pot_roast_dl_interview/)__ (19 upvotes) #huskers
    - Erik to Boise

__- by xdeathxcomoanyx on [r/Huskers](https://www.reddit.com/r/Huskers/comments/zto4pw/erik_to_boise/)__ (31 upvotes) #huskers
    - Making A "Prime" Impression

__- by shiggy402 on [r/Huskers](https://www.reddit.com/r/Huskers/comments/zt36ok/making_a_prime_impression/)__ (21 upvotes) #huskers
