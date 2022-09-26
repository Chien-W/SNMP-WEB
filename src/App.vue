<template>
  <a-layout>
    <a-layout-header class="header" style="background-color: #057cdd;height: 100px">
      <div class="logo" />
      <a-menu
          v-model:selectedKeys="selectedKeys1"
          theme="dark"
          mode="horizontal"
          :style="{ lineHeight: '64px'}"
      >
      </a-menu>
    </a-layout-header>
    <a-layout style="height: 45vw;" >
      <a-layout-sider width="200">
        <a-menu
            v-model:selectedKeys="selectedKeys2"
            v-model:openKeys="openKeys"
            mode="inline"
            :style="{ height: '100%', borderRight: 0 ,}"
        >
          <a-sub-menu key="sub1" >
            <template #icon>
              <SettingOutlined />
            </template>
            <template #title>北向连接</template>
            <a-menu-item key="1">SNMP北向</a-menu-item>
          </a-sub-menu>
        </a-menu>
      </a-layout-sider>
      <a-layout style="padding: 0 24px 24px">
        <a-breadcrumb style="margin: 16px 0">
        </a-breadcrumb>
        <a-layout-content
            :style="{ background: '#fff', padding: '24px', margin: 0, minHeight: '280px' }"
        >
        <div style="width:100%;height:100% ;border: 1px solid #adbdcd;">
          <div style="width:100%;height:7% ;">
            <a-row>
              <a-col :span="1" justify="center"></a-col>
              <a-col :span="3">
                <p style=" text-align:center;border-bottom: 10px solid #2c81c7;font-size: 17px;padding-bottom: 6px;padding-top: 5px;margin-top: 5px">SNMP北向</p>
              </a-col>
              <a-col :span="18" ></a-col>
              <a-col :span="2">
                <a-button style="width: 80%;margin-top: 10px" type="primary">保存</a-button>
              </a-col>
            </a-row>
          </div>
          <div style="height: 93.2%;border-top:1px solid black">
            <a-row style="height: 100%;margin-top: -1px">
              <a-col flex="30%" style="height: 100%">
                <div style="height:100%;border:1px solid black">
                  <div style="width:90%;height:30%;border: 1px solid black;margin-left: 25px;margin-top: 30px">
                    <p style="text-align: center;font-size: 18px;border-bottom: 1px solid black">SNMP北向</p>
                    <a-row >
                      <a-col flex="10%"></a-col>
                      <a-col style="font-size: 15px;margin-top: 55px">
                        启动SNMP北向：
                      </a-col>
                      <a-col flex="5%"></a-col>
                      <a-col style="margin-top: 55px">
                        <a-switch v-model:checked="checked1" checked-children="开" un-checked-children="关" />
                        <br />
                      </a-col>
                    </a-row>
                  </div>
                </div>
              </a-col>
              <a-col flex="auto">
                <div style="height:100%;">
                  <div style="font-size:16px;height:80%;width:80%;margin-left: 45px;margin-top:20px;">
                      <a-row>
                        <a-col :span="2"><span>系统名称:</span></a-col>
                        <a-col><a-input v-model:value="value" placeholder="Basic usage" /></a-col>
                      </a-row>
                  </div>

                </div>
              </a-col>
            </a-row>
          </div>



        </div>
        </a-layout-content>
      </a-layout>
    </a-layout>
  </a-layout>
</template>
<script>
import { CheckOutlined, CloseOutlined, SettingOutlined } from '@ant-design/icons-vue';
import {defineComponent, reactive, ref, toRefs} from 'vue';
export default defineComponent({
  components: {
    // eslint-disable-next-line vue/no-unused-components
    CheckOutlined,
    // eslint-disable-next-line vue/no-unused-components
    CloseOutlined,
    SettingOutlined,
  },

  setup() {
    const state = reactive({
      checked1: false,
      value :ref('')
    });
    return {
      selectedKeys1: ref(['2']),
      selectedKeys2: ref(['1']),
      openKeys: ref(['sub1']),
      ...toRefs(state),

    };
  },

});
</script>
<style>
#components-layout-demo-top-side-2 .logo {
  float: left;
  width: 120px;
  height: 31px;
  margin: 16px 24px 16px 0;
  background: rgba(255, 255, 255, 0.3);
}

.ant-row-rtl #components-layout-demo-top-side-2 .logo {
  float: right;
  margin: 16px 0 16px 24px;
}

</style>