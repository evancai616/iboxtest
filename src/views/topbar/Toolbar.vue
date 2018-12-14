<template>
  <div class="container">
    <v-row>
      <v-col id="title" :span="4">
        <span>{{ companyInfo.name }}</span>
        <img :src="companyInfo.imgUrl">
      </v-col>
      <v-col id="menu" :span="8">
        <v-menu>
          <v-submenu v-for="menuItem in menuInfo" :index="menuItem.index" :key="menuItem.index">
            <template slot="title">{{ menuItem.title }}</template>
            <el-menu-item v-for="submenuItem in menuItem" :index="submenuItem.index" :key="submenuItem.index">
              <template slot="title"><i class="submenuItem.icon"/></template>
              {{ submenuItem.title }}
            </el-menu-item>
          </v-submenu>
        </v-menu>
      </v-col>
      <v-col id="tool" :span="4">
        <el-dropdown v-for="(dropmenuItem, index) in dropmenuInfo" :key="index">
          <span>
            <i :class="dropmenuItem.icon"/>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>{{ dropmenuItem.title }}</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </v-col>
      <v-col id="info" :span="8">

        <span>{{ userInfo.role }}</span>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'Toolbar',
  data() {
    return {
      companyInfo: {
        name: 'IBOXCHAIN',
        imgUrl: 'http://www.ukzenith.net/images/logo.png'
      },
      menuInfo: [
        {
          title: '用户管理',
          index: '1',
          menuList: [
            { icon: 'user', title: '用户', index: '1-1' },
            { icon: 'user', title: '用户', index: '1-2' },
            { icon: 'user', title: '用户', index: '1-3' }
          ]
        },
        {
          title: '信息管理',
          index: '2',
          menuList: [
            { icon: 'user', title: '用户', index: '2-1' },
            { icon: 'user', title: '用户', index: '2-2' },
            { icon: 'user', title: '用户', index: '2-3' }
          ]
        },
        {
          title: '资料管理',
          index: '3',
          menuList: [
            { icon: 'user', title: '用户', index: '3-1' },
            { icon: 'user', title: '用户', index: '3-2' },
            { icon: 'user', title: '用户', index: '3-3' }
          ]
        }
      ],
      dropmenuInfo: [
        {
          icon: 'user',
          menuList: [
            { title: '用户' },
            { title: '用户' },
            { title: '用户' }
          ]
        },
        {
          icon: 'user',
          menuList: [
            { title: '用户' },
            { title: '用户' },
            { title: '用户' }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
  .container{
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    min-height: 30px;
    max-height: 50px;
    line-height: 1.2;
  }
</style>
