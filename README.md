<h2 align="center">
<p align="center">KtPractice</p>
<a href="https://www.hi-dhl.com">
    <img src="https://readme-typing-svg.herokuapp.com?font=Merriweather&size=30&center=true&multiline=true&width=600&height=60&lines=持+续+更+新+中.+.+.">
  </a>
</h2>

这个仓库用于实践和测试 Kotlin 、 Java 性能 和 新语法相关的代码案例，正在陆续添加新的案例。欢迎 **star**

### 反射

关于反射耗时，详细请查看文章 [揭秘反射真的很耗时吗，反射 10 万次，耗时多久](https://mp.weixin.qq.com/s/Ah8Yau_UW07s6LnGjrG4hA)

**文章摘要**

关于网上的答案都是千篇一律，比如反射慢、反射过程中频繁的创建对象占用更多内存、频繁的触发 GC 等等。

那么反射慢多少？创建 1 个对象 或者 创建 10 万个对象耗时多少？单次反射 或者 10 万次反射耗时多少。测试结果我已经放到了 **KtPractice/report/reflect** 下面了。

![](http://img.hi-dhl.com/202205072207765.png)

* 以 log 结尾的文件是生成的日志文件
* 以 json 结尾的文件，用于上传到 [JMH Visualizer](https://jmh.morethan.io/)  和 [jmh-visual-chart](http://deepoove.com/jmh-visual-chart) 进行可视化分析

反射前后的耗时，最后汇总一下 五轮 10 万次测试平均值。

|  | 正常调用 | 反射 | 反射优化后 | 反射优化后关掉安全检查 |
| --- | --- | --- | --- | --- |
| 创建对象 | 0.578 ms/op| 4.710 ms/op | 1.018  ms/op | 0.943  ms/op |
| 方法调用 | 0.422 ms/op | 10.533  ms/op | 0.844  ms/op | 0.687  ms/op |
| 属性调用 | 0.241 ms/op | 12.432 ms/op | 1.362  ms/op | 1.202  ms/op |
| 伴生对象 | 0.470 ms/op | 5.661 ms/op | 0.840  ms/op | 0.702  ms/op |

这是基于 JMH(Java Microbenchmark Harness) 测试的结果，clone 项目，运行 **ReflectBenchmark** 即可看到对应的结果。


### 后续内容正在陆续增加中...

### 联系我
 
<div align="center">
    <table>
        <tr>
             <td><a href="https://juejin.im/user/2594503168898744">掘金</a></td>
             <td><a href="https://hi-dhl.com">博客</td>
             <td><a href="https://github.com/hi-dhl">Github</a></td>
             <td><a href="https://www.zhihu.com/people/hi-dhl">知乎</a></td>
             <td><a href="https://space.bilibili.com/498153238">哔哩哔哩</a></td>
             <td><a href="https://site.51git.cn">互联网人专属导航站</a></td>
         </tr>
     </table>
</div>

* 个人微信：hi-dhl
* 公众号：ByteCode，包含 Jetpack ，Kotlin ，Android 10 系列源码，译文，LeetCode / 剑指 Offer / 多线程 / 国内外大厂算法题 等等一系列文章

<div align="center">
    <img src='http://cdn.51git.cn/2020-10-20-151047.png' width = 420px/>
</div>

## License

```
Copyright 2022 hi-dhl (Jack Deng)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```


