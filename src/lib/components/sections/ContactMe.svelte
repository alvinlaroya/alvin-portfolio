<script>
    import {
        Label,
        Input,
        Textarea,
        Button,
        Spinner,
        Toast,
    } from "flowbite-svelte";
    import { Icon } from "flowbite-svelte-icons";

    import emailjs from "@emailjs/browser";
    import HeaderTitle from "./HeaderTitle.svelte";

    let emailSent = false;
    let sending = false;

    let from_name = "";
    let from_email = "";
    let message = "";

    const sendEmail = async () => {
        sending = true;

        var templateParams = {
            from_name,
            from_email,
            message,
        };

        await emailjs
            .send(
                "service_zcz9jfs",
                "template_wrjungi",
                templateParams,
                "DUw16T85P5iAir2NQ"
            )
            .then(
                function (response) {
                    console.log("SUCCESS!", response.status, response.text);
                    sending = false;
                    emailSent = true;

                    resetForm();
                },
                function (error) {
                    console.log("FAILED...", error);
                }
            );

        setTimeout(() => (emailSent = false), 3000);
    };

    const resetForm = () => {
        from_name = "";
        from_email = "";
        message = "";
    };

    let textareaprops = {
        id: "message",
        name: "message",
        label: "Your message",
        rows: 6,
        placeholder: "Leave a message...",
    };
</script>

<HeaderTitle title="Contact Me" subtitle="Send Me A Message" />
<div class="container grid grid-cols-1 md:grid-cols-2 content-center mt-16">
    <div>
        <img src="/wp5603752.jpg" alt="" />
    </div>
    <div>
        {#if emailSent}
            <Toast
                transition="slide"
                simple
                contentClass="flex space-x-4 divide-x divide-gray-200 dark:divide-gray-700"
            >
                <Icon
                    name="papper-plane-outline"
                    class="w-5 h-5 text-green-500 dark:text-green-500 rotate-45"
                />
                <div class="pl-4 text-sm font-normal">
                    Message sent successfully.
                </div>
            </Toast>
        {/if}
        <div class="mb-6 mt-6">
            <Label for="large-input" class="block mb-2">Name</Label>
            <Input
                bind:value={from_name}
                id="large-input"
                size="lg"
                placeholder="Type your name here"
            />
        </div>
        <div class="mb-6">
            <Label for="large-input" class="block mb-2">Email</Label>
            <Input
                bind:value={from_email}
                id="large-input"
                size="lg"
                placeholder="Type your email here"
            />
        </div>
        <div>
            <Textarea bind:value={message} {...textareaprops} />
        </div>
        <div class="flex w-full justify-end">
            <Button size="lg" color="purple" on:click={sendEmail}>
                {#if sending}
                    <Spinner class="mr-3" size="4" color="white" />Sending ...
                {:else}
                    <span>Send Message</span>
                {/if}
            </Button>
        </div>
    </div>
</div>
