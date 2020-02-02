<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import TextInput from "./UI/TextInput.svelte";
  import Button from "./UI/Button.svelte";
  let formData = {
    title: "",
    subtitle: "",
    imageUrl: "",
    description: "",
    address: "",
    contactEmail: ""
  };
  let meetups = [
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
  function addMeetup() {
    const newMeetup = {
      id: Math.random().toString(),
      ...formData
    };
    meetups = [...meetups, newMeetup];
  }
  function formHandler(event) {
    formData[event.target.name] = event.target.value;
    console.log(formData);
  }
</script>

<style>
  main {
    margin-top: 5rem;
  }

  form {
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>

<Header />

<main class="main">
  <form on:submit|preventDefault={addMeetup}>
    <TextInput
      id="title"
      label="Title"
      type="text"
      name="title"
      value={formData.title}
      on:input={formHandler} />
    <TextInput
      id="subtitle"
      label="Subtitle"
      type="text"
      name="subtitle"
      value={formData.subtitle}
      on:input={formHandler} />
    <TextInput
      id="address"
      label="Address"
      type="text"
      name="address"
      value={formData.address}
      on:input={formHandler} />
    <TextInput
      id="imageUrl"
      label="Image URL"
      type="text"
      name="imageUrl"
      value={formData.imageUrl}
      on:input={formHandler} />
    <TextInput
      id="contactEmail"
      label="E-Mail"
      type="email"
      name="contactEmail"
      value={formData.contactEmail}
      on:input={formHandler} />
    <TextInput
      id="description"
      label="Description"
      controlType="textarea"
      name="description"
      value={formData.description}
      on:input={formHandler} />
    <Button type="submit" caption="Save" />
  </form>
  <MeetupGrid {meetups} />
</main>
