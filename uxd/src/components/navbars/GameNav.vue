<script setup>
import LanguageSwitcher from '../controls/LanguageSwitcher.vue'
import VolumeSwitcher from '../controls/VolumeSwitcher.vue'
import HelpModalSwitcher from '../controls/HelpModalSwitcher.vue'
import SettingsModalSwitcher from '../controls/SettingsModalSwitcher.vue'
import Logo from '../../assets/images/Logo.vue'
</script>

<template>
    <div id="nav">
        <router-link to="/">
            <div class="logo">
                <Logo/>
                <div class="logo-title">{{ $t('coinhunter.title') }}</div>
            </div>
        </router-link>
        <div class="player-info">
            <div class="player">
                <div><img :src="playerImage"></div>
                {{ playerName }}
            </div>
            <div class="points">
                {{ score }}
            </div>
        </div>
        <div class="controls">
            <HelpModalSwitcher />
            <VolumeSwitcher />
            <LanguageSwitcher />
            <SettingsModalSwitcher />
        </div>
    </div>
</template>

<script>
export default {
    props: {
        score: Number,
        playerName: String,
        playerImageNo: Number
    },
    data() {
        return {
            playerImage: "src/assets/images/Player/Player_" + this.playerImageNo + ".svg"
        }
    }
}
</script>