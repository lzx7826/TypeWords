<script setup lang="ts">
import { GITHUB, ProjectName } from "@/config/env.ts";
import BaseIcon from "@/components/BaseIcon.vue";
import { defineAsyncComponent } from "vue";

const Dialog = defineAsyncComponent(() => import('@/components/dialog/Dialog.vue'))
let showWechatDialog = $ref(false)
let showXhsDialog = $ref(false)
let showQQDialog = $ref(false)
</script>

<template>
  <div class="flex-col center gap-1">
    <BaseIcon>
      <IconFluentShare20Regular/>
    </BaseIcon>

    <a
        :href="GITHUB"
        target="_blank"
        rel="noreferrer"
        aria-label="GITHUB 项目地址">
      <BaseIcon>
        <IconSimpleIconsGithub/>
      </BaseIcon>
    </a>

    <BaseIcon @click="showWechatDialog = true">
      <IconSimpleIconsWechat class="color-green-500"/>
    </BaseIcon>
    <BaseIcon @click="showQQDialog = true">
      <IconUiwQq class="color-red"/>
    </BaseIcon>
    <BaseIcon @click="showXhsDialog = true">
      <IconSimpleIconsXiaohongshu class="color-red-500"/>
    </BaseIcon>

    <a
        href="https://x.com/typewords2"
        target="_blank"
        rel="noreferrer"
        aria-label="关注我的 X 账户 typewords2">
      <BaseIcon>
        <IconRiTwitterFill class="color-blue"/>
      </BaseIcon>
    </a>

    <a
        href="mailto:zyronon@163.com"
        target="_blank"
        rel="noreferrer"
        aria-label="发送邮件到 zyronon@163.com">
      <BaseIcon>
        <IconMaterialSymbolsMail class="color-blue"/>
      </BaseIcon>
    </a>
  </div>
  <Dialog v-model="showWechatDialog" title="Type Words 交流群">
    <div class="w-120 p-6 pt-0">
      <div class="mb-4">
        加入我们的用户社群后，您可以与我们的开发团队进行沟通，分享您的使用体验和建议，帮助我们改进产品，同时也能够及时了解我们的最新动态和更新内容。
      </div>
      <div class="text-center">
        <img src="/wechat.png" alt="微信群二维码" class="w-60 rounded-lg">
      </div>
    </div>
  </Dialog>
  <Dialog v-model="showXhsDialog" title="小红书">
    <div class="w-120 p-6 pt-0">
      <div class="mb-4">
        关注小红书后，您可以获得开发团队的最新动态和更新内容，反馈您的使用体验和建议，帮助我们改进产品，同时也能够及时了解我们的最新动态和更新内容。
      </div>
      <div class="text-center">
        <img src="/xhs.png" alt="小红书二维码" class="w-60 rounded-lg">
      </div>
    </div>
  </Dialog>
  <Dialog v-model="showQQDialog" title="QQ 交流群">
    <div class="w-120 p-6 pt-0">
      <div class="mb-4">
        <span>加入我们的用户社群后，您可以与我们的开发团队进行沟通，分享您的使用体验和建议，帮助我们改进产品，同时也能够及时了解我们的最新动态和更新内容。</span>
      </div>
      <div class="text-center">
        <img src="/qq.jpg" alt="QQ群二维码" class="w-60 rounded-lg">
      </div>
    </div>
  </Dialog>

</template>
<style scoped lang="scss">
a {
  color: unset;
}

</style>
