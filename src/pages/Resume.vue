<template>
  <div class="mx-auto p-5 flex flex-col">
    <!-- 人名 -->
    <div class="text-center text-2xl font-bold my-2">{{ name }}</div>
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
          <span><span class="font-bold">蒙彼利埃大学综合理工学校</span> - 研究生 - 计算机</span>
          <span>2012 - 2015</span>
        </div>
        <div class="flex flex-row justify-between text-sm">
          <span><span class="font-bold">武汉大学</span> - 本科 - 软件工程</span>
          <span>2008 - 2012</span>
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

const name = '傅智'
const phoneNumber = '(+86)18682108301'
const emailAddress = 'fuzhi0711@126.com'
const location = '中国-深圳'
const basics = [
  '多年前端开发，热爱前端技术，有团队管理的经验。公司级开源项目PMC',
  '丰富的Web全栈开发经验，常用技术栈: Vue2/3, ElementUI, AntD, Node.js, Koa, Egg.js，有React项目经验',
  '有管理后台微前端项目、低代码项目、国际化项目、Node BFF的开发经验。',
  '熟练使用前端工程的构建、打包、部署等工具。对后端开发语言、网络、devops有基础了解。',
  '熟练阅读英，法文档。'
]
const works = [
  {
    title: '腾讯 (高级前端开发)',
    date: ['2017.04'],
    projects: [
      {
        title: '腾讯教育乐学小鹅B侧系统- 项目前端负责人',
        items: [
          '业务背景: 为新业务（乐学小鹅app）打造全新B侧配置系统。提供完整的开课路径，实现内容的创建和配置以及课程的编排。',
          '参与B侧系统的规划, 作为需求Owner协调团队及资源，把控需求开发流程。',
          '参与系统方案设计及开发，项目采用微前端+低代码解决方案。',
          '负责部门全栈APM能力调研和规划，落地全链路监控工具，支持一键查看全链路请求视图，降低问题排查成本。',
        ]
      },
      {
        title: '腾讯视频媒资星海内容平台 - 项目前端负责人',
        items: [
          '业务背景: 星海系列平台承载腾讯视频的内容加工与运营，是连通内容生产和分发的重要环节。前端团队涉及近30多个系统的开发和维护。',
          '主导前端服务化改造，完成星海由纯页面服务（Jquery）到 Vue + EggJS 的Node服务化改造。搭建Node接入层，解耦前后端依赖。实现多协议互通，多实体数据组装，面向界面需求进行数据处理。同时协议转换层支持配置化访问不同协议接口，大大减少开发成本。',
          '负责前端工程化推动。开发和维护项目脚手架、组件库，优化开发效率。同时推进代码Code Review流程和项目CICD。',
          '推动前端可靠性建设，完善页面和Node层的监控（emonitor)、日志(atta)和告警。参与emonitor监控项目共建，设计和实现Jsonp请求监控。'
        ],
      },
      {
        title: '公司级开源项目（前端国际化） - PMC',
        items: [
          '业务背景: 为解决现有前端应用场景国际化相关问题，统一公司内国际化接入流程。搭建多语言协作平台和工具链。',
          '负责SDK整体规划、开发和项目流程控制，以及Oteam宣传，影响力建设。同时主要负责国际化Vue框架SDK和编译时SDK解决方案。',
          '负责设计和开发I18N代码编译Core。通过编译时对代码AST的处理，完成代码中词条的自动提取，自动翻译等功能。当前已支持React，Html，Vue等语言和框架的代码处理。同时通过插件生态，支持其他语言处理拓展。以编译Core为处理核心，已开发Webpack, CLI等自动化工具。',
        ],
      }
    ],
  },
  {
    title: 'Progis - 法国公司（全栈开发）',
    date: ['2015.09', '2017.01'],
    projects: [
      {
        title: 'Youmaps地图工具',
        items: [
          'Youmaps地图工具开发。参与项目数据库设计和接口开发。完成数据访问层代码重构以及前端代码模块化。日常需求迭代。',
        ]
      }
    ],
  }
]
</script>

<style scoped>
</style>