### 上传组件

> ```
> 组件名称
> ```

```
PlgUpload
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>

<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>

<script src="../../../modules/layui-master/dist/layui.all.js"></script>

<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>

<script src="../../../components/PlgUpload/codebase/PlgUpload.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
使用的方法::
    <style>
        body {
            padding: 50px 100px;
        }

        .layui-upload-img {
            width: 92px;
            height: 92px;
            margin: 0 10px 10px 0;
        }

        hr {
            margin: 30px 0;
        }
    </style>
</head>

<body>
    <div id="uploadDemo"></div>
    <script>
        // 用户选择的时候做些什么
        function chooseFn(obj) {
            console.log('chooseFn函数');
        }

        // 在上传之前做点什么
        function beforeFn(obj) {
            console.log('beforeFn');
        }

        // 在上传之前做点什么
        function doneFn(res) {
            console.log('doneFn');
        }

        // 上传产生错误的时候触发这个函数
        function errorFn() {
            console.log('errorFn');
        }

        // 多个文件上传的时候，文件全部上传成功之后调用的函数
        function allDoneFn(obj) {
            console.log('全部上传成功了');
        }

        var config = {
            renderer: 'uploadDemo',
            type: 'single', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'
            uploadParams: {
                url: 'http://httpbin.org/image',
                headers: null,
                accept: 'file',
                acceptMime: 'image/*',
                exts: "jpg|png|gif|bmp|jpeg|pdf",
                size: 10000, // 单位是kb
                method: 'get',
                fileAccept: 'image/*',
                data: { //额外参数
                    a: 1,
                    b: function () {
                        return 2
                    }
                },
            },
            chooseFn: chooseFn,
            beforeFn: beforeFn,
            doneFn: doneFn,
            errorFn: errorFn
        };

        // var plg = new PlgUpload(config);

        var config1 = {
            renderer: 'uploadDemo',
            type: 'multiple', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'

            uploadParams: {
                url: 'http://httpbin.org/image',
                multiple: true,
                headers: null,
                accept: 'file',
                acceptMime: 'image/*',
                exts: "jpg|png|gif|bmp|jpeg|pdf",
                size: 10000, // 单位是kb
                method: 'get',
                fileAccept: 'image/*',
                data: { //额外参数
                    a: 1,
                    b: function () {
                        return 2
                    }
                },
            },
            chooseFn: chooseFn,
            beforeFn: beforeFn,
            doneFn: doneFn,
            errorFn: errorFn
        };

        // var plg = new PlgUpload(config1);

        var config2 = {
            renderer: 'uploadDemo',
            type: 'multipleTable', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'
            uploadParams: {
                url: 'http://httpbin.org/image',
                accept: 'file',
                multiple: true,
                number: 3,
                auto: false,
            },
            chooseFn: chooseFn,
            beforeFn: beforeFn,
            doneFn: doneFn,
            errorFn: errorFn   
        };

        if(config2.uploadParams.multiple) {
            config2.uploadParams.allDone = allDoneFn;
        }

        // var plg = new PlgUpload(config2);

        // upload.render({
        //     elem: '#test9',
        //     url: '',
        //     done: function (res) {
        //         console.log(res);
        //     }
        // });

        // 上传【 音频/视频】文件 
        var config5 = {
            renderer: 'uploadDemo',
            type: 'multimedia', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'
            testdes: '上传音频',
            uploadParams: {
                url: '',
                accept: 'audio'
            },
            doneFn: doneFn
        }

        // var config5 = {
        //     renderer: 'uploadDemo',
        //     type: 'multimedia', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'
        //     testdes: '上传视频',
        //     uploadParams: {
        //         url: '',
        //         accept: 'audio'
        //     },
        //     doneFn: doneFn
        // }

        // var plg = new PlgUpload(config5);



        // 手动上传，选择图片和上传，分两步走
        //手动上传
        var config6 = {
            renderer: 'uploadDemo',
            type: 'manualOperation', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'

            uploadParams: {
                url: '',
                auto: false
            },
            doneFn: doneFn
        }

        // var plg = new PlgUpload(config6);


        // 拖拽/直接上传
        var config7 = {
            renderer: 'uploadDemo',
            type: 'drag', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'
            uploadParams: {
                url: '',
            },
            doneFn: doneFn
        }
        var plg = new PlgUpload(config7);

        // url: '',
        // done: function (res) {
        //     console.log(res);
        // }
        var config8 = {
            renderer: 'uploadDemo',
            type: 'origin', // 'single', 'multiple', multipleTable', 'multimedia', 'manualOperation', 'drag', 'origin'

            uploadParams: {
                url: ''

            },
            doneFn: doneFn
        }
        // var plg = new PlgUpload(config8);

    </script>
</body>
```

![](/assets/uploadOrigin.png)  
![](/assets/uploadAfter.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | elem |
| type | 是否显示百分比，【false --默认值，不展示】【true--展示】 | 布尔值 |
| chooseFn | 用户数选择的 | 百分比 |
| beforeFn | 厚度，显示进度条的大小，【默认空】可选参数【layui-progress-big】 | 字符串 |
| doneFn | 背景颜色可选【layui-bg-red】【layui-bg-orange】【layui-bg-blue】【layui-bg-green】 | 字符串 |
| errorFn | 背景颜色可选【layui-bg-red】【layui-bg-orange】【layui-bg-blue】【layui-bg-green】 | 字符串 |



