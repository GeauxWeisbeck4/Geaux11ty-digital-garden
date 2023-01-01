- # Sunday 12/18/22
- # To Do Today 
    - {{[[TODO]]}} [[JavaScript Notes Guide]]
    - {{[[DONE]]}} [[MEAN Notes]]
        - {{[[TODO]]}} [[MongoDB Notes]]
        - {{[[TODO]]}} [[Angular Notes]]
        - {{[[TODO]]}} [[Node.js Notes]]
        - {{[[TODO]]}} [[Express.js Notes]]
    - {{[[DONE]]}} [[Next.js Notes]]
        - [[Next.js Beginner Patterns Course]]
        - [[Architect an Extensible Digital Garden with Next.js, Tailwind, and NX]]
    - {{[[TODO]]}} [[Tar Heel Dev Studio]]
    - {{[[TODO]]}} [[Sell Templates]]
    - {{[[TODO]]}} Learning stuff
        - {{[[TODO]]}} [[Alpine.js Notes]]
    - {{[[TODO]]}} [[30 Days of Projects]]
        - {{[[TODO]]}}  Advent calendar
        - {{[[TODO]]}} Get going 
    - {{[[TODO]]}} [[Mean Stack Developer Paid Newsletter]]
    - {{[[TODO]]}} [[MEAN Stack Developer]]
    - {{[[TODO]]}} [[Content Calendar]]
    - # Pomodoro Flow
        - {{[[POMO]]: 25}} Finish Lume blog post
        - {{[[POMO]]: 60}} Tar Heel Dev Studio
- # Awesome Stuff
    - [Brett Victor's Website](https://worrdream.com)
    - 
- #reddit
    - Build a Realtime Chat App with Remix and Supabase

__- by iamqaz on [r/JAMstack](https://www.reddit.com/r/JAMstack/comments/znd959/build_a_realtime_chat_app_with_remix_and_supabase/)__ (14 upvotes) #react
    - If you know, you know

__- by horhorou on [r/react](https://www.reddit.com/r/react/comments/znyxyz/if_you_know_you_know/)__ (148 upvotes) #react
    - 
- #huskers
    - Build a Realtime Chat App with Remix and Supabase

__- by iamqaz on [r/JAMstack](https://www.reddit.com/r/JAMstack/comments/znd959/build_a_realtime_chat_app_with_remix_and_supabase/)__ (11 upvotes) #huskers
    - how to add animation on react fontawesome

__hey guys i am working on a project . i am use react with fontawesome icon and i want to use animation on icon 

    &lt;FontAwesomeIcon icon={faGear} size="xs"/&gt;

it's is my code i am using fontawesome react package

- by aman_mohammed on [r/react](https://www.reddit.com/r/react/comments/zonvq6/how_to_add_animation_on_react_fontawesome/)__ (1 upvotes) #huskers
    - When Im adding input it is updated in the next iteration For eg if i type A it shows nothing but when i type AB it shows A

__    FORM NAME.js
    import { useState } from "react";
    const FormName=(props)=&gt;{
    
    const [inputName,setInputName]=useState('');
    const NameHandler=event=&gt;{
    console.log(inputName)
    setInputName(event.target.value)
    props.onNameSubmit(inputName)
    
    }
    
    return(
        &lt;div&gt;
            &lt;p&gt;
                Name
            &lt;/p&gt;
            &lt;input type="text" value={inputName} onChange={NameHandler}&gt;&lt;/input&gt;
        &lt;/div&gt;
    );
    }
    export default FormName;
    
    FORM.JS
    
    import { useState } from "react";
    import Button from "./Button";
    import DisplayList from "./DisplayList";
    import FormAge from "./FormAge";
    import FormName from "./FormName";
    
    const Form = () =&gt; {
      const [enteredAge, setEnteredAge] = useState("");
      const [enteredName, setEnteredName] = useState("");
      let content = &lt;p&gt;no items&lt;/p&gt;;
      const [displayList, setDisplayList] = useState([]);
    
      const SubmitHandler = (recivedValue) =&gt; {
        if (enteredName.length &lt; 2) {
          alert("invalid name");
          return;
        }
        if (enteredAge === -1) {
          alert("invalidd age");
          return;
        }
        setDisplayList((prevDisplayList) =&gt; {
          const updateDisplayList = [...prevDisplayList];
          updateDisplayList.unshift({ name: enteredName, age: enteredAge });
          console.log(updateDisplayList);
          setEnteredAge("")
          setEnteredName("")
          return updateDisplayList;
        });
    
        // console.log(enteredAge)
      };
      const onNameSubmitHandler = (recivedName) =&gt; {
        setEnteredName(recivedName);
    
      };
    
      const onAgeSubmitHandler = (recivedAge) =&gt; {
        setEnteredAge(recivedAge);
      };
    
      if (displayList.length &gt; 0)
        content = &lt;DisplayList itemlist={displayList}&gt;&lt;/DisplayList&gt;;
      return (
        &lt;div&gt;
          &lt;FormName onNameSubmit={onNameSubmitHandler}&gt;&lt;/FormName&gt;
          &lt;FormAge onAgeSubmit={onAgeSubmitHandler}&gt;&lt;/FormAge&gt;
          &lt;Button title="Submit" onSubmit={SubmitHandler}&gt;&lt;/Button&gt;
          {content}
        &lt;/div&gt;
      );
    };
    export default Form;

- by yvg_2401 on [r/react](https://www.reddit.com/r/react/comments/zopvfv/when_im_adding_input_it_is_updated_in_the_next/)__ (2 upvotes) #huskers
    - Introducing Glue4: Eliminate Backend Headaches and Empower Your Front-End Development

__**Today, we are releasing the early beta version of** [**Glue4**](https://beta.glue4.dev/)**.**

We built Glue4 to scratch our own itch: whenever we start building an app, there’s all these different layers that need to be pieced together with subtle gotchas (auth, backend, DB, where to host, etc). The vast majority of the apps we build don’t really need anything beyond state persistence and authentication.

And that’s what Glue4 abstracts away: having to host our own backend, pick our own DB, figure out the querying language/ORM and then host &amp; maintain them all somewhere “in the cloud”. All you need to do is run a ***single npm install command*** and you get Auth + state persistence in the backend out of the box.

We built it with our use case in mind (React + Redux, using RTK’s best practices), but we’re happy to support other state management libraries down the line.

[Simply add backend persistence and auth to any app by replacing Redux](https://reddit.com/link/zovm4z/video/2ogen0h4vm6a1/player)

Let us know what you think by taking Glue4 out for a spin: either by building on top of our [skeleton app](https://github.com/glue4-dev/glue4-skeleton-app) or [take a look at the docs](https://github.com/glue4-dev/glue4-skeleton-app/wiki) on how to integrate it into your own project. We highly appreciate your candid feedback and welcome you to join our [Discord community](https://discord.gg/rTdavHJRdA) (or heck, [book us for a pairing session](https://cal.mixmax.com/petergao/glue4_support)). We can't wait to see what you build with it and stay tuned for future updates!

- by Klause-End on [r/react](https://www.reddit.com/r/react/comments/zovm4z/introducing_glue4_eliminate_backend_headaches_and/)__ (1 upvotes) #huskers
    - WR Jaylen Lloyd commits to Nebraska

__https://twitter.com/mitchsherman/status/1604196100574945281?s=46&amp;t=CawbqJUHUflG1KTwjgxJsA

- by marijohna on [r/Huskers](https://www.reddit.com/r/Huskers/comments/zodwxf/wr_jaylen_lloyd_commits_to_nebraska/)__ (90 upvotes) #huskers
    - Dylan Raiola officially decommits from Ohio State.

__- by PaperyWhistle on [r/Huskers](https://www.reddit.com/r/Huskers/comments/zoaxel/dylan_raiola_officially_decommits_from_ohio_state/)__ (348 upvotes) #huskers
    - Our HC is a top tier twitter shitposter.

__- by PaperyWhistle on [r/Huskers](https://www.reddit.com/r/Huskers/comments/zobpqy/our_hc_is_a_top_tier_twitter_shitposter/)__ (133 upvotes) #huskers
