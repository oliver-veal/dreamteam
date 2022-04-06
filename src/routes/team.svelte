<script lang="ts">
  import ChevronDown from "$lib/icon/heroicons/ChevronDown.js";
  import Icon from "$lib/icon/Icon.svelte";
  import Menu from "$lib/menu/Menu.svelte";
  import MenuIcon from "$lib/menu/MenuIcon.svelte";
  import { OnMount } from "fractils";
  import { fly, fade } from "svelte/transition";

  let menuOpen = false;

  let closeMenu = () => (menuOpen = false);

  let side_scroll;

  let pos = { top: 0, left: 0, x: 0, y: 0 };

  const mouseDownHandler = (e: MouseEvent) => {
    pos = {
      left: side_scroll.scrollLeft,
      top: side_scroll.scrollTop,
      x: e.clientX,
      y: e.clientY,
    };

    side_scroll.style.cursor = "grabbing";
    side_scroll.style.userSelect = "none";

    document.addEventListener("mousemove", mouseMoveHandler);
    document.addEventListener("mouseup", mouseUpHandler);
  };

  const mouseMoveHandler = (e: MouseEvent) => {
    const dx = e.clientX - pos.x;
    side_scroll.scrollLeft = pos.left - dx;
  };

  const mouseUpHandler = (e: MouseEvent) => {
    document.removeEventListener("mousemove", mouseMoveHandler);
    document.removeEventListener("mouseup", mouseUpHandler);

    side_scroll.style.cursor = "grab";
    side_scroll.style.removeProperty("user-select");
  };

  interface Team {
    img: string;
    name: string;
    role: string;
    blurb: string;
    skills: string[];
    offset: number;
  }

  const getRandomOffset = () => {
    return 350 + Math.random() * 100;
  };

  const team = [
    {
      img: "nick_munro",
      name: "Nick Munro",
      role: "Cheif Dreamer",
      blurb:
        "Nick is a multi award winning designer, innovator, entrepreneur who matches opportunity with talent and resource.",
      skills: ["Strategy", "Details", "Commitment"],
      offset: getRandomOffset(),
    },
    {
      img: "freya_smith",
      name: "Freya Smith",
      role: "Design Engineer",
      blurb:
        "Freya is interested in the fusion of art and creativity with engineering, generating inventive design solutions.",
      skills: ["Product Design", "User Experience Design", "Engineering"],
      offset: getRandomOffset(),
    },
    {
      img: "harika",
      name: "Harika Adivikolanu",
      role: "Experience Designer and Strategist",
      blurb:
        "Harika is an experience designer and strategist focused breaking down barriers between humans and emerging technologies. Harika uses a non-intrusive design approach in physical and digital design solutions to enhance wellbeing.",
      skills: [
        "UI/UX and Experience Design",
        "Innovation Strategy",
        "Human-Centered Research",
      ],
      offset: getRandomOffset(),
    },
    {
      img: "idan",
      name: "Idan Gal Shohet",
      role: "Branding and Communications",
      blurb:
        "Idan combines design, engineering and marketing approaches, ensuring solutions have a powerful identity that reaches, and impacts, the intended audience.",
      skills: ["Brand Development", "Communications", "Graphic design"],
      offset: getRandomOffset(),
    },
    {
      img: "jessica_riley",
      name: "Jessica Riley",
      role: "Interdisciplinary Designer and Researcher & Creative Lead",
      blurb:
        "A human-centred designer, researcher and communicator, Jessica tackles complex challenges through a holistic and collaborative approach; effecting meaningful impact through design.",
      skills: ["User-Centred Design", "Creative Strategy", "Content Design"],
      offset: getRandomOffset(),
    },
    {
      img: "julian",
      name: "Julian Ellis-Brown",
      role: "Systems Thinker and Design Engineer",
      blurb:
        "With a background in Mechanical Engineering and a double-masters in Innovation Design Engineering, Julian brings together a macro understanding of design which is underscored by a fundamental knowledge of first principles. Having spent time designing innovative new mechanical devices for DreamTeam, Julian is now turning his attention to sustainability through co-founding saltyco®, a materials science start-up focussing on turning the fashion industry planet-positive.",
      skills: [
        "Systems Design",
        "Bio-Based Materials",
        "Planet-Centred Design",
      ],
      offset: getRandomOffset(),
    },
    {
      img: "leo_planck",
      name: "Leo Planck-Prideaux",
      role: "Hardware Engineer",
      blurb:
        "Leo thrives at the intersection of technology and design. His passion is creating products that achieve their technical potential through elegant design.",
      skills: [
        "3D Modelling",
        "Integrated Circuit Design",
        "Visualisation and Rendering",
      ],
      offset: getRandomOffset(),
    },
    {
      img: "marco",
      name: "",
      role: "",
      blurb: "",
      skills: ["", "", ""],
      offset: getRandomOffset(),
    },
    {
      img: "martin_lombard",
      name: "Martin Lombard",
      role: "Design Engineer",
      blurb:
        "Martin is a passionate creator with an innovative and disruptive approach to problem-solving. He applies rigorous engineering and design concepts to create aesthetic, attractive and precise systems.",
      skills: [
        "Product Design",
        "Created Content Creation",
        "Technical Development",
      ],
      offset: getRandomOffset(),
    },
    {
      img: "oscar_leclercq",
      name: "Oscar Leclercq",
      role: "Design Engineer and Web Designer",
      blurb:
        "Oscar focuses on user-centred design and engineering, pushing this approach within the scope of sustainable innovation. Oscar has developed online platforms for Dreamteam including websites and online shops, as well as communicating Dreamteam's work to clients and the public.",
      skills: ["Communications", "Web Design", "Human-Centered Design"],
      offset: getRandomOffset(),
    },
  ];

  let selected_team: Team = team[0];
</script>

<head>
  <title> Dreamteam - Team </title>
</head>

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-50">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-xl p-2.5 md:p-5"
  >
    <a href="/" sveltekit:prefetch>
      <img src="/dreamteam.svg" alt="dreamteam" width="200" />
    </a>
    <button
      on:click={() => {
        menuOpen = !menuOpen;
      }}
      class="p-2"
    >
      <MenuIcon
        bind:open={menuOpen}
        class="w-6 xl:w-8 {menuOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

<Menu open={menuOpen} {closeMenu} />

<div
  class="relative w-full h-screen flex flex-col xl:flex-row xl:space-x-16 items-center justify-center p-8 xl:p-16"
>
  <h1
    class="text-4xl xl:text-8xl uppercase font-light text-right p-4 xl:max-w-[400px]"
  >
    Who we are
  </h1>
  <div class="flex flex-col max-w-[500px] text-center xl:text-left">
    <h2 class="text-md xl:text-2xl p-2">
      We are a collection of creatives, engineers and innovators.
    </h2>
    <h2 class="text-md xl:text-2xl p-2">
      We are a student-led professional design consultancy based in Imperial
      College London, working with the creative leadership of renowned British
      Engineer and Artist Nick Munro.
    </h2>
  </div>

  <OnMount>
    <div
      class="absolute left-1/2 top-3/4 -translate-x-1/2 -translate-y-1/2"
      in:fly={{ y: 150, duration: 1500, delay: 0 }}
    >
      <Icon src={ChevronDown} size="24" />
    </div>
  </OnMount>
</div>

<div class="w-full flex flex-col">
  <div class="flex w-full flex-grow items-center justify-center">
    <div class="relative w-full xl:max-w-[1000px] max-w-[600px] h-[600px]">
      {#each team as member}
        {#if selected_team === member}
          <div
            transition:fade|local={{ duration: 150 }}
            class="absolute inset-0 flex xl:flex-row flex-col xl:divide-x divide-y xl:divide-y-0 py-16 items-center justify-center w-full h-full"
          >
            <div class="flex flex-col space-y-8 p-8 xl:p-16 items-start">
              <div class="flex flex-col">
                <h2 class="text-3xl">{member.name}</h2>
                <p>{member.role}</p>
              </div>
              <p class="text-md xl:text-xl">
                {member.blurb}
              </p>
            </div>

            <div
              class="flex flex-col space-y-8 p-16 items-center justify-center flex-shrink-0"
            >
              {#each member.skills as skill}
                <h2>{skill}</h2>
              {/each}
            </div>
          </div>
        {/if}
      {/each}
    </div>
  </div>

  <div
    bind:this={side_scroll}
    on:mousedown={mouseDownHandler}
    class="w-full xl:h-[560px] h-[450px] overflow-y-hidden overflow-x-auto no-scrollbar cursor-grab"
  >
    <div class="flex w-full h-full">
      <div class="flex w-full items-end">
        <div class="p-8" />

        {#each team as member}
          <div
            style:background="linear-gradient(180deg,#FF827C,#FF53F6)"
            style:height={selected_team === member
              ? "600px"
              : `${member.offset}px`}
            class="{selected_team === member ||
              'xl:hover:translate-y-0 hover:translate-y-32'} xl:translate-y-16 translate-y-48 transition-all rounded-t-full p-1 xl:mx-8 mx-4"
            on:click={() => (selected_team = member)}
          >
            <div
              style:background="url(/headshots/webp/{member.img}.webp)"
              style:background-size="cover"
              alt={member.name}
              class="xl:w-[200px] w-[150px] xl:h-[200px] h-[150px] rounded-full"
            />
          </div>
        {/each}
        <div class="p-8" />
      </div>
    </div>
  </div>
</div>

<style>
  /* Hide scrollbar for Chrome, Safari and Opera */
  .no-scrollbar::-webkit-scrollbar {
    display: none;
  }

  /* Hide scrollbar for IE, Edge and Firefox */
  .no-scrollbar {
    -ms-overflow-style: none; /* IE and Edge */
    scrollbar-width: none; /* Firefox */
  }
</style>
