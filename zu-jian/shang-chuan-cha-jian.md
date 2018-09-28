### 上传组件

> 组件名称 
```
PlgUpload
```

#### tips:
- 此API需要配合后台一起测试，主要是返回参数的场景比较多
- 参考网址https://www.layui.com/doc/modules/upload.html

  

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

| 属性 | 说明 | 类型 | 默认值 |
| :--- | :--- | :--- | ---- |
| renderer | 挂载点，是id，不需要写\`\#\` | elem | 空 |
| type | 上传文件的类型，【'single'--单个文件，单个预览图】, 【'multiple'--多个文件，产生多一个预览图】, 【'multipleTable'--多个文件，产生table预览模式，分两步上传】, 【'multimedia'--不同媒体文件的上传】, 【'manualOperation'--分两步上传，需要手动点击两次】, 【'drag'--有图标的上传模式】, 【'origin'--原始的上传模式】 | string |  |
| uploadParams | 上传参数的配置 | object |  |
| uploadParams.headers | 上传路径 | string |  |
| uploadParams.url | 上传路径 | string |  |
| uploadParams.accept | 指定允许上传时校验的文件类型，可选值有：images（图片）、file（所有文件）、video（视频）、audio（音频） | string | images |
| uploadParams. acceptMime | 规定打开文件选择框时，筛选出的文件类型，值为用逗号隔开的 MIME 类型列表。如：  *acceptMime: 'image/\*'*（只显示图片文件）  *acceptMime: 'image/jpg, image/png'*（只显示 jpg 和 png 文件）默认值【images】 | string | images |
| uploadParams.exts | 允许上传的文件后缀。一般结合 *accept* 参数类设定。假设 accept 为 file 类型时，那么你设置 *exts: 'zip\|rar\|7z'* 即代表只允许上传压缩格式的文件。如果 accept 未设定，那么限制的就是图片的文件格式 | string | jpg\|png\|gif\|bmp\|jpeg |
| uploadParams. auto | 是否选完文件后自动上传。如果设定 *false*，那么需要设置 *bindAction* 参数来指向一个其它按钮提交上传 | boolean | true |
| uploadParams.  size | 设置文件最大可允许上传的大小，单位 KB。不支持ie8/9 | number | 0 （即不限制） |
| uploadParams.   multiple | 是否允许多文件上传。设置 *true*即可开启。不支持ie8/9 | boolean | false |
| uploadParams.   number | 设置同时可上传的文件数量，一般配合 multiple 参数出现。 注意：*该参数为 layui 2.2.3 开始新增* | number | 0 （即不限制） |
| chooseFn | 选择文件后的回调函数。返回一个object参数 | function |  |
| beforeFn | 文件提交上传前的回调。返回一个object参数（同上），详见下文 | function |  |
| doneFn | 执行上传请求后的回调。返回三个参数，分别为：*res*（服务端响应信息）、*index*（当前文件的索引）、*upload*（重新上传的方法，一般在文件上传失败后使用）。详见下文 | function |  |
| errorFn | 执行上传请求出现异常的回调（一般为网络异常、URL 404等）。返回两个参数，分别为：*index*（当前文件的索引）、*upload*（重新上传的方法）。详见下文 | function ||



#### Tips::

图片上传之后返回的参数
```json
{
  "code": 0
  ,"msg": ""
  ,"data": {
    "src": "http://cdn.layui.com/123.jpg"
  }
} 
```

