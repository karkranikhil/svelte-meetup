<script>
  import Header from "./UI/Header.svelte";
  import MeetupItem from "./Meetups/MeetupItem.svelte";
  const meetups = [
    {
      id: "m1",
      title: "React Melbourne",
      subtitle: "A JavaScript library for building user interfaces",
      description:
        "React JS Meetup Group - A group for those interested in React, Flux, React Router, Webpack, Javascript and other related web (and now App Native) development.",
      imageUrl:
        "https://secure.meetupstatic.com/photos/event/8/e/d/7/600_451596567.jpeg",
      address: "Melbourne, Australia",
      contactEmail: "react@melbourne.com"
    },
    {
      id: "m2",
      title: "The Melbourne F-Enders: Front End Mastery",
      subtitle: "One stop for all frontend solution",
      description:
        "F-Enders Melbourne is a community for Frontend Enthusiasts! Whether you're new to frontend development or looking to learn new tricks, we provide an environment to share learnings with the group.",
      imageUrl:
        "https://secure.meetupstatic.com/photos/event/d/d/f/e/600_472196830.jpeg",
      address: "Melbourne, Australia",
      contactEmail: "frontend@melbourne.com"
    }
  ];
</script>

<style>
  #meetups {
    margin-top: 5rem;
  }
</style>

<Header />
<section id="meetups">
  {#each meetups as meetup}
    <MeetupItem cardData={meetup} />
  {/each}
</section>
