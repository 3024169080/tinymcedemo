<template>
  <div class="about">
    <h1>tinymce</h1>
    <div>
      <editor v-model="myValue" :init="init"></editor>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
import tinymce from "tinymce";
import "tinymce/themes/silver";
import editor from "@tinymce/tinymce-vue";
import "tinymce/themes/silver";
import "tinymce/plugins/paste";
import "tinymce/plugins/image";
import "tinymce/plugins/link";
import "tinymce/plugins/code";
import "tinymce/plugins/table";
import "tinymce/plugins/lists";
import "tinymce/plugins/wordcount";
export default {
  name: "",
  props: {
    value: {
      type: String,
      default: ""
    },
    disabled: {
      type: Boolean,
      default: false
    },
    plugins: {
      type: [String, Array],
      default: "link lists image code table wordcounts"
    },
    toolbar: {
      type: [String, Array],
      default:
        "bold italic underline strikethrough | fontsizeselect fontselect | forecolor backcolor | alignleft aligncenter alignright alignjustify | bullist numlist | outdent indent blockquote | undo redo | link unlink code | removeformat"
    }
  },
  data() {
    return {
      myValue: "",
      init: {
        // content_css: "/static/plugins/tinymce/mycontent.css",
        height: "700px",
        width: "500px",
        plugins: this.plugins, //插件
        toolbar: this.toolbar, //工具栏
        branding: false, //技术支持(Powered by Tiny || 由Tiny驱动)
        menubar: true, //菜单栏
        theme: "silver", //主题
        zIndex: 1101
      }
    };
  },
  components: {
    editor
  },
  computed: {},
  created() {},
  mounted() {},
  methods: {}
};
</script>

<style lang="scss" scoped>
.about {
}
</style>
