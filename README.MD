
## 基于VUESJ/UEditor的富文本编辑器

#### 1.引入所需文件
      ```
       //如果使用了`vue-meta`等第三方类库
         metaInfo: {
            script: [
                {
                    src: "/static/libs/ue/ueditor.config.js"
                },
                {
                    src: "/static/libs/ue/ueditor.all.min.js"
                }
            ]
        },
       // 如果未使用则需再index.html内引入
      ```

#### 2.使用组件

```
npm install element-ui
```

```

import myEditor from "@/components/editor";
components: { myEditor }

<my-editor label="brief"
      class="ueditor-wrap"
      maximumWords="2000"
      :content="defaultEditorContent"
      :handleChange="handleBrief"></my-editor>

```

 - defaultEditorContent：可设置为默认文本（html）
 - handleChange:当富文本内容进行则会触发函数，返回值有如下键值对
    ```
      {
          html:editor.getContent(),
          txt:editor.getContentTxt(),
          count:wordNumber,
          exceed:wordExceed
      }
      ```