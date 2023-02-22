<template>
  <div class="container mx-auto p-5 flex flex-col">
    <div class="text-center text-4xl my-5 font-bold">{{ name }}</div>
    
    <div class="flex justify-between my-5">
      <div>Phone: (+86) 13592833907</div>
      <div>Email: chyiqm@qq.com</div>
    </div>

    <Area title="个人介绍">
      <Block>
        <Item v-for="i, idx in basics" :key="`basic_${idx}`" :content="i" />
      </Block>
    </Area>

    <Area title="工作经历">
      <div class="space-y-5">
        <Work v-for="work, idx in works" :key="`work_${idx}`" v-bind="work" />
      </div>
    </Area>

    <Area title="教育背景">
      <Block>
        <div class="flex flex-row justify-between">
          <span><span class="font-bold">北京理工大学珠海学院</span> - 信息工程</span>
          <span>2010 - 2014</span>
        </div>
      </Block>
    </Area>
  </div>
</template>

<script setup lang="ts">
import Area from './components/Area.vue';
import Block from './components/Block.vue';
import Work from './components/Work.vue';
import Item from './components/Item.vue';

const name = '李梓霖'
const works = [
  {
    title: '腾讯 (前端工程师)',
    date: ['2019年4月'],
    projects: [
      {
        title: '腾讯视频媒资星海内容平台 - 项目前端负责人',
        items: [
          '背景：星海内容平台是承载腾讯视频核心媒体资料数据的运营和加工入口。是数据从生成到对外分发的核心枢纽。',
          '负责前端需求沟通，积极推动方案落地及跟进项目进度。',
          '推动项目的可靠性建设，完善项目的监控上报及告警，提高问题定位/处理效率。',
          '责设计和落地用户行为上报，搜集分析用户行为数据，推动功能优化，提高用户体验。'
        ]
      },
      {
        title: '腾讯视频媒资功能矩阵项目 - 项目前端负责人',
        items: [
          '背景: 随着业务发展，有 30+ 独立的平台系统为媒资业务提供专项功能支撑，形成媒资功能矩阵。',
          '统一代码标准，完善项目 devops 流程，抹平不同项目间的开发差异，提高整体开发效率。',
          '主导前端服务架构优化，完成服务的前后端分离，实现页面服务的 CSR 改造，减低项目维护成本。',
          '搭建通用 Node 接入层，实现接口配置化接入，对接后端多种协议的 rpc 调用，大大减少开发成本。'
        ],
      },
      {
        title: '前端国际化 Oteam 编译核心 - 主要开发',
        items: [
          '背景：为解决现有 Web 前端应用场景国际化相关问题，统一公司内国际化接入流程。搭建多语言协作平台和工具链。',
          '负责设计和开发国际化编译核心。通过编译时对代码 AST 的处理，完成代码中词条的自动提取，自动翻译等功能。当前已支持 React，Html，Vue 等语言和框架的代码处理。同时通过插件生态，支持其他语言处理拓展。'
        ],
      }
    ],
  },
  {
    title: '深圳文思海辉信息技术有限公司（前端开发）',
    date: ['2016年8月', '2019年4月'],
    projects: [
      {
        title: '腾讯视频 - 媒资库系统',
        items: [
          '背景：媒资系统承载了腾讯视频核心媒体资料数据的内部操作入口，原平台由后台兼任开发，功能和实现相对简单。随着业务的发展，对系统的前端功能和开发质量有更高的需求',
          '完成前端项目从基于 C++ 的页面模板引擎 + jQuery 到 node + vue 的升级改造。构建基础的前端开发流程。实现更高效的开发，更好的支持业务发展。'
        ]
      }
    ],
  },
  {
    title: '深圳市创尔时装有限公司（网络技术）',
    date: ['2015年5月', '2016年7月'],
    projects: [
      {
        items: [
          '负责公司官网的搭建和维护，维护公司电脑设备及网络的正常运行。'
        ]
      }
    ],
  },
  {
    title: '北京和堂文化有限责任公司（合伙人）',
    date: ['2013年10月', '2015年5月'],
    projects: [
      {
        items: [
          '维持公司正常运行及发展'
        ]
      }
    ],
  }
]
const basics = [
  '腾讯视频媒资中心前端小团队负责人',
  '熟练掌握前端 Vue 框架，熟练掌握 NodeJs、Koa、EggJs 开发',
  '熟练使用前端工程的构建、打包、部署等工具',
  '参与公司级开源项目协同开发',
  '熟练阅读英文文档'
]
</script>

<style scoped>
</style>