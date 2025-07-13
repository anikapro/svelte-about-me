<script>
  import ImageCard from "./lib/ImageCard.svelte";
  let name = "Anika";
  let age = 19;
  let bio =
    "I'm a second year undergrad student at Northwestern University studying Computer Science and Political Science from Dallas, Texas. ";
  let bio2 =
    "I learned to code through Kode With Klossy, doing three two-week summer camps. This most recent summer, I am an Instructor Assistant for the AI/ML camp, and was a Code-A-Bration IA in the school year. I am also currently doing criminal justice reform research at the Deason Criminal Justice Reform Center in Dallas!";
  let interests = ["accessible technology", "criminal justice", "creating"];
  let cardData = [
    {
      image:
        "https://www.bookstoreinlenox.com/wp-content/uploads/2021/01/lit21-scaled.jpg",
      title: "reading & writing",
      description:
        "I love to read a variety of genres and write short stories! My favorites are Severance by Ling Ma and Parable of the Sower by Octavia Butler. ",
    },
    {
      image: "https://tse1.explicit.bing.net/th/id/OIP.gR7Tx00swdppFhHk1SgRdAHaJ3?r=0&pid=Api",
      title: "drinking coffee",
      description:
        "I love to drink different types of coffees and teas! I enjoy drinking lattes, cold brews, matchas, and boba tea.",
    },
    {
      image:
        "https://tse4.mm.bing.net/th/id/OIP.6m8lHyJsImYULaqW8zfYqwHaJ3?r=0&pid=Api",
      title: "listening to music",
      description:
        "I love listening to new music and going to concerts! My favorite bands right now are Wednesday, MJ Lenderman, and Chanel Beads. ",
    },
  ];

  import { fade } from "svelte/transition";

  let visible = $state(false);
</script>

<div class="container">
  <h1>Anika Proddutoor</h1>
  <p>Hello, my name is <strong>{name}</strong>!</p>
  <p>I'm <strong>{age}</strong> years old.</p>
  <p>{bio}</p>
  <p>{bio2}</p>
  <p>
    Check out my <a
      href="https://www.linkedin.com/in/anikaproddutoor"
      class="link"
    >
      LinkedIn
    </a>
  </p>
  <p>
    Check out <a
      href="https://www.youtube.com/playlist?list=PL1B627337ED6F55F0"
      class="link"
    >
      NPR Tiny Desk Concerts
    </a>
  </p>

  <h2>My Interests</h2>
  <label>
    <input type="checkbox" bind:checked={visible} />
    Click to see my interests~
  </label>
  {#if visible}
    <div class="interests" transition:fade>
      {#each interests as interest}
        <div class="interest">{interest}</div>
      {/each}
    </div>
  {/if}
  <h2>Some of my favorite things :p</h2>
  <div class="card-container">
    {#each cardData as { image, title, description }}
      <ImageCard {image} {title} {description} />
    {/each}
  </div>
</div>

<style>
  h1 {
    color: #9093ea;
    font-family: Arial, Helvetica, sans-serif;
    font-style: italic;
  }
  .container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
    font-family: Arial, Helvetica, sans-serif;
  }
  .interests {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }
  .interest {
    background-color: #9093ea;
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
  }
</style>
