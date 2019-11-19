<template>
    <div class="green-player" ref="green_player">
        <audio :id="audio_id" :class="audio_class">
            <source :src="source"/>
        </audio>
    </div>
</template>

<script>
import GreenAudioPlayer from 'green-audio-player';

export default {
    name: "VueGreenAudioPlayer",
    props: {
        source: String,
        audio_class: String,
        audio_id: String,
        stop_others_on_play: {type: Boolean, default: true, required: false},
        show_download_button: {type: Boolean, default: true, required: false},
    },
    mounted() {
        let vm = this;
        new GreenAudioPlayer($(vm.$refs.green_player)[0], {
            stopOthersOnPlay: this.stop_others_on_play,
            showDownloadButton: this.show_download_button
        });
    }
};
</script>
