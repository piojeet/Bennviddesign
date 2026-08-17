<template>
    <div class="card credentials-card" role="button" tabindex="0" @click="go" @keydown.enter="go">
        <div class="card-img">
            <img :src="imgSrc" style="width: 100%" alt="Credentials Icon" />
        </div>

        <div class="card-content">
            <h6>More About Me</h6>
            <h4>Credentials</h4>

            <svg xmlns="http://www.w3.org/2000/svg" class="enter-btn" width="20" height="20" viewBox="0 0 24 24"
                fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M13 17l5-5-5-5M6 17l5-5-5-5" />
            </svg>
        </div>
    </div>
</template>

<script setup>
import { useRouter } from "vue-router";
import credLogo from "@/assets/img/cred-logo1.png";

const props = defineProps({
    to: { type: String, default: "/credentials" },
    imgSrc: { type: [String, Object], default: credLogo },
});

const router = useRouter();
const go = () => router.push(props.to);
</script>
