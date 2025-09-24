<template>
  <n-modal v-model:show="showModal">
    <n-card
      style="width: 90%; max-width: 600px"
      title="关于本站"
      :bordered="false"
      size="huge"
      role="dialog"
      aria-modal="true"
    >
      <template #header-extra>
        <n-button quaternary circle @click="showModal = false">
          <template #icon>
            <Icon name="icon:close" />
          </template>
        </n-button>
      </template>

      <div class="about-content">
        <n-space vertical :size="16">
          <div class="section">
            <h3>站点监测</h3>
            <p>这是一个简约的站点状态监控页面，基于 UptimeRobot API 构建，实时显示各个服务的运行状态和可用性数据。</p>
          </div>

          <div class="section">
            <h3>功能特性</h3>
            <ul>
              <li>实时监控多个站点的运行状态</li>
              <li>显示详细的可用性统计数据</li>
              <li>支持多种监控类型（HTTP、PING、端口等）</li>
              <li>响应式设计，支持各种设备</li>
              <li>支持暗色模式切换</li>
              <li>多语言支持</li>
            </ul>
          </div>

          <div class="section">
            <h3>技术栈</h3>
            <p>基于 Nuxt 3 + Vue 3 + Naive UI 构建，使用 UptimeRobot API 获取监控数据。</p>
          </div>

          <div class="section">
            <h3>开源信息</h3>
            <p>
              本项目基于开源协议发布，源代码托管在
              <n-button text type="primary" @click="openLink('https://github.com/imsyy/site-status')">
                GitHub
              </n-button>
            </p>
          </div>
        </n-space>
      </div>

      <template #footer>
        <n-flex justify="end">
          <n-button @click="showModal = false">关闭</n-button>
        </n-flex>
      </template>
    </n-card>
  </n-modal>
</template>

<script setup lang="ts">
const showModal = defineModel<boolean>();

const openLink = (url: string) => {
  window.open(url, "_blank");
};
</script>

<style lang="scss" scoped>
.about-content {
  .section {
    h3 {
      color: var(--n-title-text-color);
      font-size: 16px;
      font-weight: 600;
      margin-bottom: 8px;
    }

    p {
      color: var(--n-text-color);
      line-height: 1.6;
      margin: 0;
    }

    ul {
      color: var(--n-text-color);
      line-height: 1.6;
      margin: 0;
      padding-left: 20px;

      li {
        margin-bottom: 4px;
      }
    }
  }
}
</style>
