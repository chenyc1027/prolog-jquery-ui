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
| type | 上传文件的类型，【'single'--单个文件，单个预览图】, 【'multiple'--多个文件，产生多一个预览图】, 【'multipleTable'--多个文件，产生table预览模式，分两步上传】, 【'multimedia'--不同媒体文件的上传】, 【'manualOperation'--分两步上传，需要手动点击两次】, 【'drag'--有图标的上传模式】, 【'origin'--原始的上传模式】 | string |
| uploadParams | 上传参数的配置 |  |
| uploadParams.headers | 上传路径 | string |
| uploadParams.url | 上传路径 | string |
| uploadParams.accept | 指定允许上传时校验的文件类型，可选值有：images（图片）、file（所有文件）、video（视频）、audio（音频） | string |
|  | uploadParams.acceptMime | 规定打开文件选择框时，筛选出的文件类型，值为用逗号隔开的 MIME 类型列表。如： |

acceptMime: 'image/\*'（只显示图片文件）   
acceptMime: 'image/jpg, image/png'（只显示 jpg 和 png 文件） | callBack |  
| uploadParams.exts \| 上传参数的配置 \| callBack \|  
| uploadParams.size \| 上传参数的配置 \| callBack \|  
| uploadParams.method \| 上传参数的配置 \| callBack \|  
| uploadParams.fileAccept \| 上传参数的配置 \| callBack \|  
| uploadParams.data \| 上传后带的参数 \| callBack \|  
| uploadParams.auto \| 选定图片之后是否直接上传【false】【true】 \| boolean \|

| chooseFn \| 用户选择了上传文件后触发的回掉函数 \| callBack |  
\| beforeFn \| 上传文件前触发的函数 \| callBack \|  
\| doneFn \| 图片上传完成后出发的效果 \| callBack \|  
\| allDonerFn \| 多个文件上传全部成功出 \| callBack \|  
\| errorFn \| 上传途中出错触发的效果 \| callBack \|

