# excel2json

原帮助文档请见：[https://neil3d.github.io/coding/excel2json.html](https://neil3d.github.io/coding/excel2json.html)

## 命令行参数

* -e, –-excel Required. 输入的Excel文件路径.
* -o, –-json 指定输出的json文件路径.
* -h, –-header Required. 表格中有几行是表头.
* -c, –-encoding (Default: utf8-nobom) 指定编码的名称.
* -l, –-lowcase (Default: false) 自动把字段名称转换成小写格式.
* -a 序列化成数组
* -d, --date:指定日期格式化字符串，例如：dd / MM / yyy hh: mm:ss
* -t 序列化时强制带上sheet name，即使只有一个sheet
* -x, --exclude_prefix： 导出时，排除掉包含指定前缀的表单和列，例如：-exclude_prefix #
* -j, --cell_json：自动识别单元格中的Json对象和Json数组，Default：false
* -s, --sever_data: 通过header中是否有server或者client 判断 是否导出server数据，还是 client数据

示例:
mono ./excel2json.exe -e ./ExampleData.xlsx -o ./ExampleData.json -a -h4 -x# -j -s
注释：
* 在mac 环境中 使用mono 运行exe文件执行excel2json 命令
* -e 转化ExapmleData.xlsx 文件
* -o 生成目标为ExampleData.json的文件
* -a 把table生成arrary的形式，如果需要也可以生成字典的形式，方便调用
* -h4 表头有4行，第五行才开始读取数据
* -x# sheet名字前面如果有# 还是表头的第一个有# 那么都忽略导出
* -j 把如果可以生成json的列都生成json格式，方便支持多种数据格式
* -s 只导出服务端数据，忽略行中有client字段的内容

    