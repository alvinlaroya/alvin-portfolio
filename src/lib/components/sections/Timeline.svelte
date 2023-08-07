<script>
  import { Timeline, TimelineItem, Button } from "flowbite-svelte";
</script>

<div class="mt-[2rem] md:mt-[15rem] md:my-28">
  <div class="text-center" data-aos="fade-up">
    <h1 class="text-4xl">Timeline</h1>
    <p>Seminar/Training Attended</p>
  </div>
</div>
<div class="flex justify-center">
  <Timeline>
    <TimelineItem
      title="Vue JS Workshop @ DMMMSU SLUC"
      date="March 2023"
      data-aos="fade-left"
    >
      <p
        class="mb-4 text-base font-normal text-gray-500 dark:text-gray-400"
        data-aos="fade-left"
      >
        Training computer science students on how to create a progressive web
        applications using Vue js.
      </p>
      <Button
        data-aos="fade-left"
        color="alternative"
        on:click={() =>
          window.open(
            "https://www.facebook.com/photo?fbid=665112145418366&set=pcb.665117418751172",
            "_blank"
          )}
        >Learn more<svg
          class="ml-2 w-3 h-3"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
          ><path
            fill-rule="evenodd"
            d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
            clip-rule="evenodd"
          /></svg
        ></Button
      >
    </TimelineItem>
    <TimelineItem title="Application UI code in Tailwind CSS" date="March 2022">
      <p class="text-base font-normal text-gray-500 dark:text-gray-400">
        All of the pages and components are first designed in Figma and we keep
        a parity between the two versions even as we update the project.
      </p>
    </TimelineItem>
    <TimelineItem title="Application UI code in Tailwind CSS" date="April 2022">
      <p class="text-base font-normal text-gray-500 dark:text-gray-400">
        Get started with dozens of web components and interactive elements built
        on top of Tailwind CSS.
      </p>
    </TimelineItem>
  </Timeline>
</div>
