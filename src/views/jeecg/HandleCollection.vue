<template>
  <a-card :bordered="false" :class="{'abcdefg':true}"></a-card>
  <!--</page-layout>-->
</template>
<script>
import ACol from "ant-design-vue/es/grid/Col";
import ARow from "ant-design-vue/es/grid/Row";
import ATextarea from "ant-design-vue/es/input/TextArea";

export default {
  components: {
    ATextarea,
    ARow,
    ACol
  },
  name: "Printgzsld",
  props: {
    reBizCode: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      columns: [{}],
      labelCol: {
        xs: { span: 24 },
        sm: { span: 2 }
      },
      wrapperCol: {
        xs: { span: 24 },
        sm: { span: 8 }
      },
      previewImage: "",
      fileList: [],
      url: {}
    };
  },
  created() {
    this.getDate();
  },
  methods: {
    loadData() {},
    getDate() {
      // 当前时间
    },
    handleCancel() {
      this.previewVisible = false;
    },
    handlePreview(file) {
      this.previewImage = file.url || file.thumbUrl;
      this.previewVisible = true;
    },
    handleChange({ fileList }) {
      this.fileList = fileList;
    }
  }
};
</script>
<style scoped>
.abcdefg .ant-card-body {
  margin-left: 0%;
  margin-right: 0%;
  margin-bottom: 1%;
  border: 0px solid black;
  min-width: 800px;
}
.explain {
  text-align: left;
  margin-left: 50px;
}
.explain .ant-input,
.sign .ant-input {
  font-weight: bolder;
  text-align: center;
  border-left-width: 0px !important;
  border-top-width: 0px !important;
  border-right-width: 0px !important;
}
.explain div {
  margin-bottom: 10px;
}
/* you can make up upload button and sample style by using stylesheets */
.ant-upload-select-picture-card i {
  font-size: 32px;
  color: #999;
}

.ant-upload-select-picture-card .ant-upload-text {
  margin-top: 8px;
  color: #666;
}
</style>