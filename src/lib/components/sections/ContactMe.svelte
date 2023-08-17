<script>
    import { Label, Input, Textarea, Button } from "flowbite-svelte";

    import emailjs from "@emailjs/browser";
    import HeaderTitle from "./HeaderTitle.svelte";

    let from_name = "";
    let from_email = "";
    let message = "";

    const sendEmail = async () => {
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
                },
                function (error) {
                    console.log("FAILED...", error);
                }
            );
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
<div class="flex container mx-auto mt-16">
    <div class="w-1/2 mx-auto">
        <div class="mb-6">
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
            <Button size="lg" color="purple" on:click={sendEmail}
                >Send Message</Button
            >
        </div>
    </div>
</div>
