<template>
  <div class="mx-auto p-5 flex flex-col">
    <!-- 人名 -->
    <div class="text-center text-3xl font-bold my-2">{{ name }}</div>
    <!-- 联系信息 -->
    <div class="flex justify-between">
      <div><IconPhone class="inline" />{{ phoneNumber }}</div>
      <div><IconEmail class="inline"/>{{ emailAddress }}</div>
      <div><IconLocation class="inline"/>{{ location }}</div>
    </div>
    <!-- 个人介绍 -->
    <Area title="个人介绍">
      <template #icon><IconMe class="inline" /></template>
      <Block>
        <Item v-for="i, idx in basics" :key="`basic_${idx}`" :content="i" />
      </Block>
    </Area>
    <!-- 工作经历 -->
    <Area title="工作经历">
      <template #icon><IconTeam class="inline" /></template>
      <Block class="space-y-3">
        <Work v-for="work, idx in works" :key="`work_${idx}`" v-bind="work" />
      </Block>
    </Area>
    <!-- 教育背景 -->
    <Area title="教育背景">
      <template #icon><IconSchool class="inline" /></template>
      <Block>
        <div class="flex flex-row justify-between text-sm">
          <span><span class="font-bold">北京理工大学珠海学院</span> - 本科 - 信息工程</span>
          <span>2010 - 2014</span>
        </div>
      </Block>
    </Area>
  </div>
</template>

<script setup lang="ts">
import Area from './components/Area.vue'
import Block from './components/Block.vue'
import Work from './components/Work.vue'
import Item from './components/Item.vue'
import IconEmail from '~icons/mdi/email'
import IconPhone from '~icons/mdi/phone'
import IconSchool from '~icons/mdi/school'
import IconTeam from '~icons/mdi/account-group'
import IconMe from '~icons/mdi/account'
import IconLocation from '~icons/mdi/map-marker'

const name = '李梓霖'
const phoneNumber = '(+86)13592833907'
const emailAddress = 'chyiqm@qq.com'
const location = '中国-深圳'
const basics = [
  '多年前端开发，热爱前端技术，有大厂、外企、创业经历，有团队管理的经验。',
  '丰富的Web全栈开发经验，常用技术栈: Vue2/3, ElementUI, AntD, Node.js, Koa, Egg.js，有React, Typescript项目经验',
  '有管理后台、低代码项目、国际化项目、Node BFF的开发经验。',
  '熟练使用前端工程的构建、打包、部署等工具。对后端开发语言、网络、devops有基础了解。',
  '熟练阅读英文文档，良好的英文交流能力。'
]
const works = [
  {
    title: 'Crypto.com (量化开发工程师-前端 / Dev Lead)',
    date: ['2022.04'],
    projects: [
      {
        title: '交易数据中台 - 项目Leader',
        items: [
          '业务背景: 交易数据中台为交易员提供交易资金转账申请管理，盘后数据统计，内部风险控制管理，及时风险告警等功能。保证交易部门在风险可控的情况下可以快速发展。',
          '单独负责数据中台前端部分的开发，维护，优化。',
          '领导后端服务的开发、技术设计以及负责部分后端功能的开发。',
          '把原先多个业务场景不同但功能相近的任务执行服务进行整合和优化。实现服务的及时异常告警，实现服务的回放、重跑能力。减少对业务测可能造成的影响，减低了开发维护成本。',
          '领导后端服务的优化、设计，保证中台服务的可靠性，提高中台开发效率。与各业务方沟通制定业务目标，开发规划。管理日常开发的项目进展。',
        ]
      }
    ]
  },
  {
    title: '腾讯 (前端工程师)',
    date: ['2019.04', '2022.04'],
    projects: [
      {
        title: '腾讯视频媒资星海内容平台 - 项目前端负责人',
        items: [
          '业务背景: 星海内容平台是承载腾讯视频核心媒体资料数据的运营和加工入口。是数据从生成到对外分发的核心枢纽。',
          '负责前端需求沟通，积极推动方案落地及跟进项目进度。',
          '推动项目的可靠性建设，完善项目的监控上报及告警，提高问题定位/处理效率。',
          '负责设计和落地用户行为上报，搜集分析用户行为数据，推动功能优化，提高用户体验。'
        ]
      },
      {
        title: '腾讯视频媒资功能矩阵项目 - 项目前端负责人',
        items: [
          '业务背景: 随着业务发展，有 30+ 独立的平台系统为媒资业务提供专项功能支撑，形成媒资功能矩阵。',
          '统一代码标准，完善项目 devops 流程，抹平不同项目间的开发差异，提高整体开发效率。',
          '主导前端服务架构优化，完成服务的前后端分离，实现页面服务的 CSR 改造，减低项目维护成本。',
          '搭建通用 Node 接入层，实现接口配置化接入，对接后端多种协议的 rpc 调用，大大减少开发成本。'
        ],
      },
      {
        title: '前端国际化 Oteam 编译核心 - 主要开发',
        items: [
          '业务背景: 为解决现有 Web 前端应用场景国际化相关问题，统一公司内国际化接入流程。搭建多语言协作平台和工具链。',
          '负责设计和开发国际化编译核心。通过编译时对代码 AST 的处理，完成代码中词条的自动提取，自动翻译等功能。当前已支持 React，Html，Vue 等语言和框架的代码处理。同时通过插件生态，支持其他语言处理拓展。'
        ],
      }
    ],
  },
  {
    title: '深圳文思海辉信息技术有限公司（前端开发）',
    date: ['2016.08', '2019.04'],
    projects: [
      {
        title: '腾讯视频 - 媒资库系统',
        items: [
          '业务背景: 媒资系统承载了腾讯视频核心媒体资料数据的内部操作入口，原平台由后台兼任开发，功能和实现相对简单。随着业务的发展，对系统的前端功能和开发质量有更高的需求。',
          '完成前端项目从基于 C++ 的页面模板引擎 + jQuery 到 node + vue 的升级改造。构建基础的前端开发流程。实现更高效的开发，更好的支持业务发展。'
        ]
      }
    ],
  },
  {
    title: '深圳市创尔时装有限公司（网络技术）',
    date: ['2015.05', '2016.07'],
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
    date: ['2013.10', '2015.05'],
    projects: [
      {
        items: [
          '维持公司正常运行及发展'
        ]
      }
    ],
  }
]
</script>

<style scoped>
</style>