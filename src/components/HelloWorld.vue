<template>
  <div class="editor">
    <CKEditor :editor="editor" v-model="output" :config="editorConfing" />
    <pre>{{ output }}</pre>
  </div>
</template>

<script>
import CKEditor from "@ckeditor/ckeditor5-vue2";
import ckeditorBuild from "@/plugins/ckeditor.js";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: {
    CKEditor: CKEditor.component,
  },
  data() {
    return {
      editor: ckeditorBuild,
      editorConfing: {
        toolbar: {
          items: [
            "heading",
            "|",
            "bold",
            "italic",
            "link",
            "bulletedList",
            "numberedList",
            "|",
            "outdent",
            "indent",
            "|",
            "imageUpload",
            "blockQuote",
            "insertTable",
            "undo",
            "redo",
            "fontColor",
            "alignment",
          ],
        },
        language: "en",
        image: {
          toolbar: [
            "imageTextAlternative",
            "imageStyle:full",
            "imageStyle:side",
          ],
        },
        table: {
          contentToolbar: ["tableColumn", "tableRow", "mergeTableCells"],
        },
        licenseKey: "",
      },
      output: "",
    };
  },
};
</script>
