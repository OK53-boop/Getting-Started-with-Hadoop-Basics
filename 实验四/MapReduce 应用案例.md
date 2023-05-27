1.
配置本机主机名为 hadoop，sudo 时需要输入 shiyanlou 用户的密码。将 hadoop 添加到最后一行的末尾。

sudo vim /etc/hosts
# 将hadoop添加到最后一行的末尾，修改后类似：（使用 tab 键添加空格）
# 172.17.2.98 f738b9456777 hadoop
ping hadoop

使用如下命令启动 Hadoop：

cd /app/hadoop-1.1.2/bin
./start-all.sh
jps # 查看启动的进程，确保 NameNode 和 DataNode 都有启动

测试数据包括两个文件 dept（部门）和 emp（员工），其中各字段用逗号分隔：
请结合生活中的例子详细分析一下。

好的，让我结合一个生活中的例子来详细分析一下。

假设我们是一家电商公司，我们需要对我们的销售数据进行分析以便更好地了解我们的客户和市场趋势。我们可以使用Hadoop系统来处理和分析大量的销售数据。

我们可以销售数据存储在两个文件中，一个文件包含有关部门的信息，另一个文件包含有关员工的信息。每个文件中的字段都用逗号分隔，例如，部门文件中的字段可能包括部门ID、部门名称和部门经理，而员工文件的字段可能包括员工ID、员工姓名、所属部门和销售额等信息。

我们可以使用Hadoop系统来处理这些文件，以便进行各种分析，例如，我们可以使用MapReduce程序来计算每个部门的总销售额，或者计算每个员工的平均销售额。我们还可以使用Hive或Pig等工具来执行更高级的分析，例如，使用机器学习算法来预测未来的销售趋势。

作为系统工程师，我们需要确保Hadoop系统已正确配置，并且正在处理的数据准确且与预期用例相关。我们还需要确保系统能够处理大量的数据，并且能够在合理的时间内完成分析任务。我们还需要考虑系统的可靠性和安全性，以确保数据不会丢失或被未经授权的人访问。





2.
配置主机名为 hadoop，sudo 时需要输入 shiyanlou 用户的密码。将 hadoop 添加到最后一行的末尾。

sudo vim /etc/hosts
# 将hadoop添加到最后一行的末尾，修改后类似：（使用 tab 键添加空格）
# 172.17.2.98 f738b9456777 hadoop
ping hadoop

使用如下命令启动 Hadoop：

cd /app/hadoop-1.1.2/bin
./start-all.sh
jps # 查看启动的进程，确保 NameNode 和 DataNode 都有启动

测试数据包括两个文件 dept（部门）和 emp（员工），其中各字段用逗号分隔：

dept 文件内容：

10,ACCOUNTING,NEW YORK
20,RESEARCH,DALLAS
30,SALES,CHICAGO
40,OPERATIONS,BOSTON

emp 文件内容：

7369,SMITH,CLERK,7902,17-12月-80,800,,20
7499,ALLEN,SALESMAN,7698,20-2月-81,1600,300,30
7521,WARD,SALESMAN,7698,22-2月-81,1250,500,30
7566,JONES,MANAGER,7839,02-4月-81,2975,,20
7654,MARTIN,SALESMAN,7698,28-9月-81,1250,1400,30
7698,BLAKE,MANAGER,7839,01-5月-81,2850,,30
7782,CLARK,MANAGER,7839,09-6月-81,2450,,10
7839,KING,PRESIDENT,,17-11月-81,5000,,10
7844,TURNER,SALESMAN,7698,08-9月-81,1500,0,30
7900,JAMES,CLERK,7698,03-12月-81,950,,30
7902,FORD,ANALYST,7566,03-12月-81,3000,,20
7934,MILLER,CLERK,7782,23-1月-82,1300,,10

在 /home/shiyanlou/install-pack/class6 目录可以找到这两个文件，把这两个文件上传到 HDFS 中 /class6/input 目录中，执行如下命令：

cd /home/shiyanlou/install-pack/class6
hadoop fs -mkdir -p /class6/input
hadoop fs -copyFromLocal dept /class6/input
hadoop fs -copyFromLocal emp /class6/input
hadoop fs -ls /class6/input

请结合生活中的例子详细分析一下。

好的，让我结合一个生活中的例子来详细分析一下。

假设我们是一家电商公司，我们需要对我们的销售数据进行分析以便更好地了解我们的客户和市场趋势。我们可以Hadoop系统来处理和分析大量的销售数据。

在这个例子中，我们有两个文件，一个包含有关部门的信息另一个包含有关员工的信息。我们需要将这些文件上传到Hadoop分布式文件系统（HDFS）中，以便我们可以使用adoop系统来处理和分析这些数据。

我们可以使用以下命令将这些文件上传到HDFS中：

cd /home/shiyanlou/install-pack/class6
hadoop fs -mkdir -p /class6/input
hadoop fs -copyFromLocal dept /class6/input
hadoop fs -copyFromLocal emp /class6/input
hadoop fs -ls /class6/input

第一行命令创建了一个名为 /class6/input 的目录，如果该目录不存在，则会自动创建。第二行和第三行命令将 dept 和 emp 文件从本地文件系统复制到 HDFS 中的 /class6/input 目录中。最后一行命令用于验证文件是否已成功上传到 HDFS 中。

一旦文件已经上传到 HDFS 中，我们可以使用Hadoop系统来处理和分析这些数据。例如，我们可以使用MapReduce程序来计算每个部门的总销售额，或者计算每个员工的平均销售额。我们还可以使用Hive或Pig等工具来执行更高级的分析，例如，使用机器学习算法来预测未来的销售趋势。

作为系统工程师，我们需要确保Hadoop系统已正确配置，并且正在处理的数据准确且与期用例相关。我们还需要确保系统能够处理大量的数据，并且能够在合理的时间内完成分析任务。我们还需要考系统的可靠性和安全性，以确保数据不会丢失或被未经授权的人访问。



3.
问题分析

MapReduce 中的 join 分为好几种，比如有最常见的 reduce side join、map side join 和 semi join 等。reduce join 在 shuffle 阶段要进行大量的数据传输，会造成大量的网络 IO 效率低下，而 map side join 在处理多个小表关联大表时非常有用 。
请结合生活中的例子详细分析一下。

好的，让我结合一个生活中的例子来详细分析一下。

假设我们是一家电商公司，我们需要对我们的销售数据进行分析以便更好地了解我们的客户和市场趋势。我们有两个数据集，一个包含有关客户的信息，另一个包含有关订单的信息。我们需要将这两个数据集进行关联，以便我们可以了解每个客户的订单情况。

在这个例子中，我们可以使用MapReduce中的join操作来将这两个数据集进行关联。reduce side join是最常见的join操作，它需要在shuffle阶段进行大量的数据传输，这会导致网络IO效率低下。但是，如果我们使用map side join，我们可以避免这种情。

在map side join中，我们可以将一个小的数据集加载到内存中，并将其作为缓存。然后，我们可以将另一个大数据集分成小块，并将每个块发送到不同的map任务中。每个map任务都可以使用缓存中的小数据集来进行关联操作，这样就避免了大量的数据传输和网络IO。

在我们的电商公司的例子中，我们可以将客户数据集加载到内存中，并将订单数据集分成小块。然后，我们可以将每个订单块发送到不同的map任务中，并使用缓存中的客户数据集来进行关联操作。这样，我们就可以避免大量的数据传输和网络IO，从而提高MapReduce作业的效率。

除了map side join，还有其他类型的join操作，例如semi join。semi join可以用于过滤掉不需要的数据，从而减少数据传输和处理的时间。在我们的电商公司的例子中，我们可以使用semi join来过滤掉不需要的订单数据，例如已取消的订单或已退货的订单。这样，我们就可以减少数据传输和处理的时间，从而提高MapReduce作业的效率。




4.
Map side join 是针对以下场景进行的优化：两个待连接表中，有一个表非常大，而另一个表非常小，以至于小表可以直接存放到内存中。这样我们可以将小表复制多份，让每个 map task 内存中存在一份（比如存放到 hash table 中），然后只扫描大表，对于大表中的每一条记录 key/value，在 hash table 中查找是否有相同的 key 的记录，如果有，则连接后输出即可。为了支持文件的复制，Hadoop 提供了一个类 DistributedCache，使用该类的方法如下：

用户使用静态方法 DistributedCache.addCacheFile() 指定要复制的文件，它的参数是文件的 URI（如果是 HDFS 上的文件，可以这样：hdfs://jobtracker:50030/home/XXX/file）。JobTracker 在作业启动之前会获取这个 URI 列表，并将相应的文件拷贝到各个 TaskTracker 的本地磁盘上。
用户使用 DistributedCache.getLocalCacheFiles() 方法获取文件目录，并使用标准的文件读写 API 读取相应的文件。

请结合生活中的例子详细分析一下。

好的，让我再结合一个生活中的例子来详细分析一下。

假设我们是一家在线教育公司，我们需要对我们学生数据进行分析以便更好地了解我们的学生和市场趋势。我们有两个数据集，一个包含有关学生信息，另一个包含有关课程的信息。我们需要将这两个数据集进行关联，以便我们可以了解每个学生的课程情况。

这个例子中，我们可以使用MapReduce中的join操作来将这两个数据集进行关联。由于学生数据集通常比课程数据集小得多，我们可以使用map side join来优化这个过程。

首先，我们可以将学生数据集加载到内存中，并将其作为缓存。然，我们可以将课程数据集分成小块，并将每个块发送到不同的map任务中。每个map任务都可以使用缓存中的生数据集来进行关联操作，这样就避免了大量的数据传输和网络IO。

为了支持文件的复制，我们可以使用Hadoop提供的DistributedCache类。我们可以使用静态方法DistributedCache.addCacheFile()指定要复制的文件，它的参数是文件的URI。JobTracker在作业启动之前会获取这个URI列表，并将相应的文件拷贝到各个TaskTracker的本地磁盘上。

在我们的在线教育公司的例子中，我们可以将学生数据集存储在HDFS上，并使用DistributedCache.addCacheFile()方法将其复制到各个TaskTracker的本地磁盘上。然后，我们可以将课程数据集分成小块，并将每个块发送到不同的map任务中。每个map任务都可以使用缓存中的学生数据集来进行关联操作，这样就避免了大量的数据传输和网络IO。

最后，我们可以使用DistributedCache.getLocalCacheFiles()方法获取文件目录，并使用标准的文件读写API读取相应的文件。这样，我们就可以在MapReduce作业中使用map side join来优化数据关联操作，从而提高作业的效率。






5.
在下面代码中，将会把数据量小的表（部门 dept) 缓存在内存中，在 Mapper 阶段对员工部门编号映射成部门名称，该名称作为 key 输出到 Reduce 中，在 Reduce 中按照部门计算各个部门的总工资。
请结合生活中的例子详细分析一下。

好的，让我结合一个生活中的例子来详细分析一下。

假设我们是一家零售公司，我们需要对我们的销售数据进行分析以便更好地了解我们的销售情况。我们有两个数据集，一个包含有关员工信息，另一个包含有关部门的信息。我们需要将这两个数据集进行关联，以便我们可以了解每个部门的销售情况。

这个例子中，我们可以使用MapReduce中的join操作来将这两个数据集进行关联。由于部门数据集通常比员工数据集小得多，我们可以使用map side join来优化这个过程。

首先，我们可以将部门数据集加载到内存中，并将其作为缓存。然后，我们可以将员工数据集分成小块，并将每块发送到不同的map任务中。每个map任务都可以使用缓存中的部门数据集来进行关联操作，这样就避免了量的数据传输和网络IO。

在Mapper阶段，我们可以将员工部门编号映射成部门名称，并将部门名称作为key输出到Reduce中。在Reduce中，我们可以按照部门计算各个部门的总工资。

为了支持文件的复制，我们可以使用Hadoop提供的DistributedCache类。我们可以使用静态方法DistributedCache.addCacheFile()指定要复制的文件，它的参数是文件的URI。JobTracker在作业启动之前会获取这个URI列表，并将相应的文件拷贝到各个TaskTracker的本地磁盘上。

在我们的零售公司的例子中，我们可以将部门数据集存储在HDFS上，并使用DistributedCache.addCacheFile()方法将其复制到各个TaskTracker的本地磁盘上。然后，我们可以将员工数据集分成小块，并将每个块发送到不同的map任务中。每个map任务都可以使用缓存中的部门数据集来进行关联操作，这样就避免了大量的数据传输和网络IO。

最后，在Reduce阶段，我们可以按照部门计算各个部门的总工资。这样，我们就可以在MapReduce作业中使用map side join来优化数据关联操作，从而提高作业的效率。





6.
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q1SumDeptSalary extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {

        // 用于缓存 dept文件中的数据
        private Map<String, String> deptMap = new HashMap<String, String>();
        private String[] kv;

        // 此方法会在Map方法执行之前执行且执行一次
        @Override
        protected void setup(Context context) throws IOException, InterruptedException {
            BufferedReader in = null;
            try {

                // 从当前作业中获取要缓存的文件
                Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
                String deptIdName = null;
                for (Path path : paths) {

                    // 对部门文件字段进行拆分并缓存到deptMap中
                    if (path.toString().contains("dept")) {
                        in = new BufferedReader(new FileReader(path.toString()));
                        while (null != (deptIdName = in.readLine())) {

                            // 对部门文件字段进行拆分并缓存到deptMap中
                            // 其中Map中key为部门编号，value为所在部门名称
                            deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                        }
                    }
                }
            } catch (IOException e) {
                e.printStackTrace();
            } finally {
                try {
                    if (in != null) {
                        in.close();
                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }

public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {

            // 对员工文件字段进行拆分
            kv = value.toString().split(",");

            // map join: 在map阶段过滤掉不需要的数据，输出key为部门名称和value为员工工资
            if (deptMap.containsKey(kv[7])) {
                if (null != kv[5] && !"".equals(kv[5].toString())) {
                    context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[5].trim()));
                }
            }
        }
    }

    public static class Reduce extends Reducer<Text, Text, Text, LongWritable> {

public void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {

            // 对同一部门的员工工资进行求和
            long sumSalary = 0;
            for (Text val : values) {
                sumSalary += Long.parseLong(val.toString());
            }

            // 输出key为部门名称和value为该部门员工工资总和
            context.write(key, new LongWritable(sumSalary));
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称、Mapper和Reduce类
        Job job = new Job(getConf(), "Q1SumDeptSalary");
        job.setJobName("Q1SumDeptSalary");
        job.setJarByClass(Q1SumDeptSalary.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为缓存的部门数据路径、第2个参数为员工数据路径和第3个参数为输出路径
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
        FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q1SumDeptSalary(), args);
        System.exit(res);
    }
}
请分别详细分析每一句代码。


好的，让我来逐行分析这段代码。

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
```
这部分代码是导入所需的Java类和包。

```java
public class Q1SumDeptSalary extends Configured implements Tool {
```
这里定义了一个名为Q1SumDeptSalary的类，它继承了Configured和Tool两个类。

```java
public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {
```
这里定义了一个名为MapClass的静态内部类，它继承了Mapper类，并指定了输入键、输入值、输出键和输出值的类型。

```java
private Map<String, String> deptMap = new HashMap<String, String>();
private String[] kv;
```
这里定义了一个名为deptMap的HashMap对象，用于缓存部门数据集。同时，定义了一个名为kv的String数组，用于存储员工数据集中的字段。

```java
@Override
protected void setup(Context context) throws IOException, InterruptedException {
    BufferedReader in = null;
    try {
        Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
        String deptIdName = null;
        for (Path path : paths) {
            if (path.toString().contains("dept")) {
                in = new BufferedReader(new FileReader(path.toString()));
                while (null != (deptIdName = in.readLine())) {
                    deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                }
            }
        }
    } catch (IOException e) {
        e.printStackTrace();
    } finally {
        try {
            if (in != null) {
                in.close();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
这里定义了一个名为setup的方法，它会在Map方法执行之前执行且执行一次。这个方法中，我们从DistributedCache中获取缓存的部门数据集，并将其存储到deptMap中。

```java
public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
    kv = value.toString().split(",");
    if (deptMap.containsKey(kv[7])) {
        if (null != kv[5] && !"".equals(kv[5].toString())) {
            context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[5].trim()));
        }
    }
}
```
这里定义了一个名为map的方法，它会对员工数据集中的字段进行拆分，并使用缓存的门数据集进行关联操作。如果员工数据集中的部门编号在部门数据集中存在，则将员工工资和部门名称作为输出键值对写入上下文中。

```java
public static class Reduce extends Reducer<Text, Text, Text, LongWritable> {
```
这里定义了一个名为Reduce的静态内部类，它继承了Reducer类，并指定了输入键、输入值、输出键和输出值的类型。

```java
public void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
    long sumSalary = 0;
    for (Text val : values) {
        sumSalary += Long.parseLong(val.toString());
    }
    context.write(key, new LongWritable(sumSalary));
}
```
这里定义了一个名为reduce的方法，它会对同一部门的员工工资进行求和，并将部门名称和该部门员工工资总和作为输出键值对写入上下文中。

```java
@Override
public int run(String[] args) throws Exception {
    Job job = new Job(getConf(), "Q1SumDeptSalary");
    job.setJobName("Q1SumDeptSalary");
    job.setJarByClass(Q1SumDeptSalary.class);
    job.setMapperClass(MapClass.class);
    job.setReducerClass(Reduce.class);
    job.setInputFormatClass(TextInputFormat.class);
    job.setOutputFormatClass(TextOutputFormat.class);
    job.setOutputKeyClass(Text.class);
    job.setOutputValueClass(Text.class);
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
    FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
    FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));
    job.waitForCompletion(true);
    return job.isSuccessful() ? 0 : 1;
}
```
这里定义了一个名为run的方法，它会实例化作业对象，并设置作业名称、Mapper和Reduce类、输入格式类、输出格式、输出键和输出值的类型等参数。然后，它会从命令行参数中获取缓存的部门数据集路径、员工数据集路径和输出路径，并将它们设置为作业的输入和输出路径。最后，它会等待作业完成并返回作业的执行结果。

```java
public static void main(String[] args) throws Exception {
    int res = ToolRunner.run(new Configuration(), new Q1SumDeptSalary(), args);
    System.exit(res);
}
```
这里定义了一个名为main的方法，它会调用ToolRunner.run()方法来运行作业，并将执行结果作为程序的退出状态。





7.
编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q1SumDeptSalary.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q1SumDeptSalary.java 文件）。

cd /app/hadoop-1.1.2/myclass
mkdir class6 && cd class6
vi Q1SumDeptSalary.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q1SumDeptSalary.java

把编译好的代码打成 jar 包（如果不打成 jar 形式运行会提示 class 无法找到的错误）。

jar cvf ./Q1SumDeptSalary.jar ./Q1SumDept*.class
mv *.jar ../..
rm Q1SumDept*.class
请详细分析一下每一句话


好的，让我来逐行分析这段代码。

```bash
cd /app/hadoop-1.1.2/myclass
mkdir class6 && cd class6
vi Q1SumDeptSalary.java
```
这里进入/app/hadoop-1.1.2/myclass目录，并创建一个名为class6的目录，并进入该目。然后，使用vi编辑器创建一个名为Q1SumDeptSalary.java的Java程序。

```bash
javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q1SumDeptSalary.java
```
里使用javac编译Q1SumDeptSalary.java程序，并使用-classpath参数指定编译时所需的类路径。这里的类路径包括hadoop-core-1.1.2.jar和commons-cli-1.2.jar两个文件。

```bash
jar cvf ./Q1SumDeptSalary.jar ./Q1SumDept*.class
```
这里使用jar命令将编译好的Q1SumDeptSalary程序打包成一个名为Q1SumDeptSalary.jar的可执行JAR文件。这里使用-cvf参数指定打包方式，并使用./Q1Sum*.class指定要打包的所有Q1SumDept开头的class文件。

```bash
mv *.jar ../..
rm Q1SumDept*.class
```
这里使用mv命令将打包好的Q1SumDeptSalary.jar文件移动到/app/hadoop-1.1.2目录下，并使用rm命令删除所有Q1SumDept开头的class文件。





8.
运行并查看结果

运行 Q1SumDeptSalary 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径参数需要全路径，否则运行会报错：

部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率。
员工数据路径：hdfs://hadoop:9000/class6/input/emp。
输出路径：hdfs://hadoop:9000/class6/out1。
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q1SumDeptSalary.jar Q1SumDeptSalary hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out1
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out1 目录，打开 part-r-00000 文件。

hadoop fs -ls /class6/out1
hadoop fs -cat /class6/out1/part-r-00000

可以看到运行结果：

ACCOUNTING 8750
RESEARCH 6775
SALES 9400
请详细分析一下每一句话。


好的，让我来逐行分析这段代码。

```bash
cd /app/hadoop-1.1.2
```
这里进入/app/hadoop-1.1.2目录。

```bash
hadoop jar1SumDeptSalary.jar Q1SumDeptSalary hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out1
```
这里使用hadoop命令来运行Q1SumDeptSalary程序，并指定部门数据路径、员工数据路径和输出路径三个参数。这里jar参数指定要运行的JAR文件，使用Q1SumDeptSalary参数指定要运行的类名。

```bash
hadoop fs -ls /class6/out1
```
这里使用hadoop fs命令来列出/class6/out1目录下的所有文件。

```bash
hadoop fs -cat /class6/out1/part-r-00000
```
这里使用hadoop命令来查看输出文件part-r-00000的内容。





9.
问题分析

求各个部门的人数和平均工资，需要得到各部门工资总数和部门人数，通过两者相除获取各部门平均工资。首先和问题 1 类似在 Mapper 的 Setup 阶段缓存部门数据，然后在 Mapper 阶段抽取出部门编号和员工工资，利用缓存部门数据把部门编号对应为部门名称，接着在 Shuffle 阶段把传过来的数据处理为部门名称对应该部门所有员工工资的列表，最后在 Reduce 中按照部门归组，遍历部门所有员工，求出总数和员工数，输出部门名称和平均工资。
请详细分析一下。

好的，让我来详细分析一下。

这个问题需要求各个部门的人数和平均工资，需要得到各部门工资总数和部门人数，通过两者相除获取各部门平均工资。为了实现这个功能，可以采用 MapReduce 编程模型，具体实现如下：

1. 在 Mapper 的 Setup 阶段缓存部门数据，这样可以在 Mapper 阶段把部门编号转换为部门名称2. 在 Mapper 阶段，抽取出部门编号和员工工资，利用缓存部门数据把部门编号对应为部门名称。

3. 在 Shuffle 阶段，把传过来的数据处理为部门名称对应该部门所有员工工资的列表。

4. 在 Reduce 阶段，按照部门归组，遍历部门所有员工，求出总数和员工数，输出部门名称和平均工资。

具体实现过程如下：

Mapper 阶段：

1. 在 Mapper 的 Setup 阶段，使用 DistributedCache 技术缓存部门数据，这样可以在 Mapper 阶段把部门编号转换为部门名称。

2. 在 Mapper 的 Map 阶段，抽取出部门编号和员工工资，利用缓存部门数据把部门编号对应为部门名称。

3. 将部门名称和员工工资作为 Mapper 的输出，输出格式为 <Text, DoubleWritable>。

Shuffle 阶段：

1. 在 Shuffle 阶段，按照部门名称对 Mapper 的输出进行排序和分组，得部门名称对应该部门所有员工工资的列表。

Reduce 阶段：

1. 在 Reduce 阶段，遍历部门所有员工，求出总数和员工数，输出部门名称和平均工资。

2. 输出格式为 <Text, Text>，其中 Text 表示部门名称，Text 表示该部门的平均工资通过以上步骤，就可以实现求各个部门的人数和平均工资的功能。






10.
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q2DeptNumberAveSalary extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {

        // 用于缓存 dept文件中的数据
        private Map<String, String> deptMap = new HashMap<String, String>();
        private String[] kv;

        // 此方法会在Map方法执行之前执行且执行一次
        @Override
        protected void setup(Context context) throws IOException, InterruptedException {
            BufferedReader in = null;
            try {
                // 从当前作业中获取要缓存的文件
                Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
                String deptIdName = null;
                for (Path path : paths) {

                    // 对部门文件字段进行拆分并缓存到deptMap中
                    if (path.toString().contains("dept")) {
                        in = new BufferedReader(new FileReader(path.toString()));
                        while (null != (deptIdName = in.readLine())) {

                            // 对部门文件字段进行拆分并缓存到deptMap中
                            // 其中Map中key为部门编号，value为所在部门名称
                            deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                        }
                    }
                }
            } catch (IOException e) {
                e.printStackTrace();
            } finally {
                try {
                    if (in != null) {
                        in.close();
                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }

    public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {

            // 对员工文件字段进行拆分
            kv = value.toString().split(",");

            // map join: 在map阶段过滤掉不需要的数据，输出key为部门名称和value为员工工资
            if (deptMap.containsKey(kv[7])) {
                if (null != kv[5] && !"".equals(kv[5].toString())) {
                    context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[5].trim()));
                }
            }
        }
    }

    public static class Reduce extends Reducer<Text, Text, Text, Text> {

    public void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {

            long sumSalary = 0;
            int deptNumber = 0;

            // 对同一部门的员工工资进行求和
            for (Text val : values) {
                sumSalary += Long.parseLong(val.toString());
                deptNumber++;
            }

            // 输出key为部门名称和value为该部门员工工资平均值
    context.write(key, new Text("Dept Number:" + deptNumber + ", Ave Salary:" + sumSalary / deptNumber));
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称、Mapper和Reduce类
        Job job = new Job(getConf(), "Q2DeptNumberAveSalary");
        job.setJobName("Q2DeptNumberAveSalary");
        job.setJarByClass(Q2DeptNumberAveSalary.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为缓存的部门数据路径、第2个参数为员工数据路径和第3个参数为输出路径
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
        DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
        FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q2DeptNumberAveSalary(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。

好的，让我来逐行分析一下代码。

1. 导入需要的包：

```
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
```

2. 定义Mapper类：

```
public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {
```

这里定义了一个Mapper类，继承自Mapper类，并指定了输入键、输入值、输出键和输出值的类型。

3. 定义缓存变量和部门数据读取方法：

``private Map<String, String> deptMap = new HashMap<String, String>();
private String[] kv;

@Override
protected void setup(Context context) throws IOException, InterruptedException {
    BufferedReader in = null;
    try {
        Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
        String deptIdName = null;
        for (Path path : paths) {
            if (path.toString().contains("dept")) {
                in = new BufferedReader(new FileReader(path.toString()));
                while (null != (deptIdName = in.readLine())) {
                    deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                }
            }
        }
    } catch (IOException e) {
        e.printStackTrace();
    } finally {
        try {
            if (in != null) {
                in.close();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

这里定义了一个Map类型的变量deptMap，用于缓存部门数据。在setup()方法中，首先通过DistributedCache.getLocalCacheFiles()方法获取缓存的文件路径，然后读取部门数据文件，将部门编号和部门名称存储到deptMap中。

4. 定义Mapper类的map()方法：

```
public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
    kv = value.toString().split(",");
    if (deptMap.containsKey(kv[7])) {
        if (null != kv[5] && !"".equals(kv[5].toString())) {
            context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[5].trim()));
        }
    }
}
```

这里定义了Mapper类的map()方法，用于将员工数据中的部门编号转换为部门名称，并输出部门名称和员工工资。在map()方法中，首先将员工数据按照逗号进行拆分，然后判断部门编号是否在deptMap中存在，如果存在，则将部门编号转换为部门名称，并将部门名称作为key，员工工资作为value，输出到Reducer。

5. 定义Reducer类：

```
public static class Reduce extends Reducer<Text, Text, Text, Text> {
```

这里定义了一个Reducer类，继承自Reducer类，并指定了输入键、输入值、输出键和输出值的类型。

6. 定义Reducer类的reduce()方法：

```
 void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
    long sumSalary = 0;
    int deptNumber = 0;
    for (Text val : values) {
        sumSalary += Long.parseLong(val.toString());
        deptNumber++;
    }
    context.write(key, new Text("Dept Number:" + deptNumber + ", Ave Salary:" + sumSalary / deptNumber));
}
```

这里定义了Reducer类的reduce()方法，用于计算每个部门的平均工资，并输出部门名称和平均工资。在reduce()方法中，首先遍历同一部门的所有员工工资，出该部门的工资总数和员工人数，然后计算平均工资，并将部门名称和平均工资输出。

7.现Tool接口：

```
public class Q2DeptNumberAveSalary extends Configured implements Tool {
```

这里定义了一个类Q2DeptNumberAveSalary，实现了Tool接口，用于处理命令行参数和运行作业。

8. 实现run()方法：

```
@Override
public int run(String[] args) throws Exception {
    Job job = new Job(getConf(), "Q2DeptNumberAveSalary");
    jobJobName("Q2DeptNumberAveSalary");
    job.setJarByClass(Q2DeptNumberAveSalary.class);
    job.setMapperClass(MapClass.class);
    job.setReducerClass(Reduce.class);
    job.setInputFormatClass(TextInputFormat.class);
    job.setOutputFormatClass(TextOutputFormat.class);
    job.setOutputKeyClass(Text.class);
    job.setOutputValueClass(Text.class);
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
    FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
    FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));
    job.waitForCompletion(true);
    return job.isSuccessful() ? 0 : 1;
}
```

这里实现了Tool接口的run()方法，用于运行作业。在run()方法中，首先实例化一个Job对象，并设置作业名称、Mapper和Reducer类。然后设置输入格式、输出格式类、输出键类型和输出值类型。接着，从命令行参数中获取缓存的部门数据路径、员工数据路径和输出路径，并将部门数据文件添加到istributedCache中。最后，运行作业并返回作业执行结果。

9. 实现main()方法：

```
public static void main(String[] args) throws Exception {
    int res = ToolRunner.run(new Configuration(), new Q2DeptNumberAveSalary(), args);
    System.exit(res);
}
```

这里实现了main()方法，用于启动作业。在main()方法中，首先调用ToolRunner.run()方法运行作业将作业执行结果保存到res变量中。然后，根据作业执行结果退出程序。






11.
3.2.4 编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q2DeptNumberAveSalary.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q2DeptNumberAveSalary.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q2DeptNumberAveSalary.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q2DeptNumberAveSalary.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q2DeptNumberAveSalary.jar ./Q2DeptNum*.class
mv *.jar ../..
rm Q2DeptNum*.class
请结合详细分析一下每一句话


好的，让我来逐行分析一下代码。

1. 进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q2DeptNumberAveSalary.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/QDeptNumberAveSalary.java 文件）。

```
cd /app/hadoop-1.1.2/myclass/class6
vi Q2DeptNumberAveSalary.java
```

这里进入指定目录，并使用vi编辑器创建一个名为Q2DeptNumberAveSalary.java的文件，用于存储程序代码。

2. 编译代码：

```
javac -classpath ../../adoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q2DeptNumberAveSalary.java
```

这里使用javac命令编译Q2NumberAveSalary.java文件，并指定类路径为../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar，以便编译器能够找到所需的类。

3. 把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

``jar cvf ./Q2DeptNumberAveSalary.jar ./Q2DeptNum*.class
```

这里使用jar命令将编译好的Q2DeptNumberAveSalary.class文件打包成Q2DeptNumberAveSalary.jar文件，并指定打包的文件名和文件路径。注意，这里使用了通配符*，以便打包所有以Q2DeptNum开头的class文件。

4. 将打包好的jar文件移动到上一级目录。

```
mv *.jar ../..
```

这里使用mv命令将打包好的jar文件移动到上一级目录。

5. 删除编译好的class文件。

```
rm Q2DeptNum*.class
```

这里使用rm命令删除编译好的Q2DeptNum.class文件，以便下次重新编译。






12.
运行并查看结果

运行 Q2DeptNumberAveSalary 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率
员工数据路径：hdfs://hadoop:9000/class6/input/emp
输出路径：hdfs://hadoop:9000/class6/out2
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q2DeptNumberAveSalary.jar Q2DeptNumberAveSalary hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out2
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out2 目录。

hadoop fs -ls /class6/out2
hadoop fs -cat /class6/out2/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

ACCOUNTING    Dept Number:3,Ave Salary:2916
RESEARCH    Dept Number:3,Ave Salary:2258
SALES    Dept Number:6,Ave Salary:1566
每句话都详细分析一下。


这段话是一段关于如何运行一个 Hadoop MapReduce 任务的指南。该任务的目的是计算每个部门的平均工资，并将结果输出定的路径中。在运行任务之前，需要确保输入路径和输出路径都是正确的，并且在 HDFS 中存在。运行命令时指定输入路径、输出路径和任务的 jar 文件路径。运行成功后，可以通过命令查看输出路径中的结果文件，并打开文件查看计算结果。

具体来说，首先需要进入 Hadoop 安装目录，然后使用 hadoop jar 命令运行 Q2DeptNumberAveSalary 任务，并指定部门数据路径、员工数据路径和输出路径。在运行任务之前，需要确输入路径和输出路径都是正确的，并且在 HDFS 中存在。运行成功后，可以使用 hadoop fs -ls 命令查看输出路径中的文件，并使用 hadoop fs -cat 命令打开文件查看计算结果。在本例中，结果文件名为 part-r-00000，其中包含每个部门的平均工资。





13.
运行并查看结果

运行 Q2DeptNumberAveSalary 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率
员工数据路径：hdfs://hadoop:9000/class6/input/emp
输出路径：hdfs://hadoop:9000/class6/out2
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q2DeptNumberAveSalary.jar Q2DeptNumberAveSalary hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out2
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out2 目录。

hadoop fs -ls /class6/out2
hadoop fs -cat /class6/out2/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

ACCOUNTING    Dept Number:3,Ave Salary:2916
RESEARCH    Dept Number:3,Ave Salary:2258
SALES    Dept Number:6,Ave Salary:1566
请详细分析一下每一句话。

这段文本是一段关于运行 Hadoop MapReduce 任务的指南。作为一个系统工程师，我需要提供准确和相关的信息来解释这段指南。

首先，这段指南提到了运行 Q2DeptNumberAveSalaryReduce 任务所需的三个参数：部门数据路径、员工数据路径和输出路径。这些参数需要在运行命令时提供。需要的是，hdfs 路径参数需要使用全路径，否则会导致运行错误。

其次，指南提到了部门数据路径和员工数据路径的位置。这些数据将被用于运行 MapReduce 任务。部门数据将被缓存在各个运行任务的节点中，以提高处理效率。

然后，指南提供了运行 MapReduce 任务的命令。这个命令包括了 Q2DeptNumberAveSalary.jar 文件的路径和三个参数。这个命令将在 Hadoop 集群上运行 MapReduce 任务。

接下来，指南提到了刷新输出路径的命令。这个命令将刷新输出路径，以便查看运行结果。

最后，指南提供了查看运行结果的命令。这个命令将列出输出路径中的文件，并显示运行结果。运行结果包括了每个部门的部门编号和平均工资。





14.
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q3DeptEarliestEmp extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {

        // 用于缓存 dept文件中的数据
        private Map<String, String> deptMap = new HashMap<String, String>();
        private String[] kv;

        // 此方法会在Map方法执行之前执行且执行一次
        @Override
        protected void setup(Context context) throws IOException, InterruptedException {
            BufferedReader in = null;
            try {
                // 从当前作业中获取要缓存的文件
                Path[] paths =     DistributedCache.getLocalCacheFiles(context.getConfiguration());
                String deptIdName = null;
                for (Path path : paths) {
                    if (path.toString().contains("dept")) {
                        in = new BufferedReader(new FileReader(path.toString()));
                        while (null != (deptIdName = in.readLine())) {

                            // 对部门文件字段进行拆分并缓存到deptMap中
                            // 其中Map中key为部门编号，value为所在部门名称
                            deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                        }
                    }
                }
            } catch (IOException e) {
                e.printStackTrace();
            } finally {
                try {
                    if (in != null) {
                        in.close();
                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            kv = value.toString().split(",");

            // map join: 在map阶段过滤掉不需要的数据
            // 输出key为部门名称和value为员工姓名+","+员工进入公司日期
            if (deptMap.containsKey(kv[7])) {
                if (null != kv[4] && !"".equals(kv[4].toString())) {
                    context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[1].trim()                     + "," + kv[4].trim()));
                }
            }
        }
    }

    public static class Reduce extends Reducer<Text, Text, Text, Text> {

        public void reduce(Text key, Iterable<Text> values, Context context) throws IOException,         InterruptedException {

            // 员工姓名和进入公司日期
            String empName = null;
            String empEnterDate = null;

            // 设置日期转换格式和最早进入公司的员工、日期
            DateFormat df = new SimpleDateFormat("dd/MM/yy");

            Date earliestDate = new Date();
            String earliestEmp = null;

            // 遍历该部门下所有员工，得到最早进入公司的员工信息
            for (Text val : values) {
                empName = val.toString().split(",")[0];
                empEnterDate = val.toString().split(",")[1].toString().trim();
                try {
                    System.out.println(df.parse(empEnterDate));
                    if (df.parse(empEnterDate).compareTo(earliestDate) < 0) {
                        earliestDate = df.parse(empEnterDate);
                        earliestEmp = empName;
                    }
                } catch (ParseException e) {
                    e.printStackTrace();
                }
            }

            // 输出key为部门名称和value为该部门最早进入公司员工
            context.write(key, new Text("The earliest emp of dept:" + earliestEmp + ", Enter             date:" + new SimpleDateFormat("yyyy-MM-dd").format(earliestDate)));
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q3DeptEarliestEmp");
        job.setJobName("Q3DeptEarliestEmp");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q3DeptEarliestEmp.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为缓存的部门数据路径、第2个参数为员工数据路径和第三个参数为输出路径
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
        FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q3DeptEarliestEmp(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。


该代码是一个使用Hadoop MapReduce实现的部门员工数据处理程序，目的是找到每个部门中最早进入公司的员工。

以下是代码的详细分析：

1. 导入必要的Java类和包：

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
```

2. 定义Map阶段的Mapper类：

```java
public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {
    // 用于缓存 dept文件中的数据
    private Map<String, String> deptMap = new HashMap<String, String>();
    private String[] kv;

    // 此方法会在Map方法执行之前执行且执行一次
    @Override
    protected void setup(Context context) throws IOException, InterruptedException {
        // 从当前作业中获取要缓存的文件
        Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
        BufferedReader in = null;
        try {
            String deptIdName = null;
            for (Path path : paths) {
                if (path.toString().contains("dept")) {
                    in = new BufferedReader(new FileReader(path.toString()));
                    while (null != (deptIdName = in.readLine())) {
                        // 对部门文件字段进行拆分并缓存到deptMap中
                        // 其中Map中key为部门编号，value为所在部门名称
                        deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                    }
                }
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (in != null) {
                    in.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }

    public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
        // 对员工文件字段进行拆分
        kv = value.toString().split(",");

        // map join: 在map阶段过滤掉不需要的数据
        // 输出key为部门名称和value为员工姓名+","+员工进入公司日期
        if (deptMap.containsKey(kv[7])) {
            if (null != kv[4] && !"".equals(kv[4].toString())) {
                context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[1].trim() + "," + kv[4].trim()));
            }
        }
    }
}
```

该Mapper类实现了Map阶段的逻辑。在setup()方法中，首先通过DistributedCache获取到部门信息文件，然后将部门编号和名称缓存到deptMap中。在map()方法中，先对员工信息进行拆分，然后通过deptMap过滤掉不属于当前部门的员工信息，最后将部门名称作为key，员工姓名和进入公司日期作为value输出。

3. 定义Reduce阶段的Reducer类：

```java
public static class Reduce extends Reducer<Text, Text, Text, Text> {
    public void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
        // 员工姓名和进入公司日期
        String empName = null;
        String empEnterDate = null;

        // 设置日期转换格式和最早进入公司的员工、日期
        DateFormat df = new SimpleDateFormat("dd/MM/yy");
        Date earliestDate = new Date();
        String earliestEmp = null;

        // 遍历该部门下所有员工，得到最早进入公司的员工信息
        for (Text val : values) {
            empName = val.toString().split(",")[0];
            empEnterDate = val.toString().split(",")[1].toString().trim();
            try {
                if (df.parse(empEnterDate).compareTo(earliestDate) < 0) {
                    earliestDate = df.parse(empEnterDate);
                    earliestEmp = empName;
                }
            } catch (ParseException e) {
                e.printStackTrace();
            }
        }

        // 输出key为部门名称和value为该部门最早进入公司员工
        context.write(key, new Text("The earliest emp of dept:" + earliestEmp + ", Enter date:" + new SimpleDateFormat("yyyy-MM-dd").format(earliestDate)));
    }
}
```

该Reducer类实现了Reduce阶段的逻辑。对于每个部门，遍历该部门下所有员工的进入公司日期信息，找到最早的那个员工，然后将该员工的姓名和进入公司日期输出。

4. 实现Tool接口和main()方法：

```java
public class Q3DeptEarliestEmp extends Configured implements Tool {
    @Override
    public int run(String[] args) throws Exception {
        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q3DeptEarliestEmp");
        job.setJobName("Q3DeptEarliestEmp");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q3DeptEarliestEmp.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为缓存的部门数据路径、第2个参数为员工数据路径和第三个参数为输出路径
        String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
        DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
        FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q3DeptEarliestEmp(), args);
        System.exit(res);
    }
}
```

该类实现了Tool接口，并且在main()方法中通过ToolRunner.run()方法来运行MapReduce作业。在run()方法中，首先实例化作业对象，并设置作业名称、Mapper和Reducer类、输入输出格式类等信息。然后通过DistributedCache将部门信息文件缓存到作业中，设置输入路径和输出路径，最后等待作业完成并返回运行结果。在main()方法中，通过ToolRunner.run()方法来运行作业，并退出程序。





15.
编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q3DeptEarliestEmp.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q3DeptEarliestEmp.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q3DeptEarliestEmp.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q3DeptEarliestEmp.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q3DeptEarliestEmp.jar ./Q3DeptEar*.class
mv *.jar ../..
rm Q3DeptEar*.class
请详细分析一下每一句话。

好的，让我来解释一下每一句话的含义：

1. 进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q3DeptEarliestEmp.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q3DeptEarliestEmp.java 文件）。

这话的意思是进入指定目录，并在该目录下新建一个名为 Q3DeptEarliestEmp.java 的程序代码文件。

2. cd /app/hadoop-1.1.2/myclass/class6

这句话的意思是切换当前工作目录 /app/hadoop-1.1.2/myclass/class6 目录下。

3. vi Q3DeptEarliestEmp.java

这句话的意思是使用 vi 编辑器打开 Q3DeptEarliestEmp.java 文件，以便编写程序代码。

4. javac -classpath ../../hadoop-core-1.1.2.jar../../lib/commons-cli-1.2.jar Q3DeptEarliestEmp.java

这句话的意思是使用 javac 命令编译 Q3DeptEarliestEmp.java 文件，并指定编译时需要使用的类路径（classpath）。

5. jar cvf ./Q3DeptEarliestEmp.jar ./Q3DeptEar*.class

这句话的意思是使用 jar 命令将编译好的 Q3DeptEarliestEmp.java 文件打包成一个名为 Q3DeptEarliestEmp.jar 的 jar 包，并将该 jar 包放在当前目录下。

6. mv *.jar ../..

这句话的意思是将当前目录下的所有 jar 包移动到上一级目录。

7. rm Q3DeptEar*.class

这句话的意思是删除当前目录下所有以 Q3DeptEar 开头的 .class 文件，以便下次重新编译。




16.
运行并查看结果

运行 Q3DeptEarliestEmp 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率
员工数据路径：hdfs://hadoop:9000/class6/input/emp
输出路径：hdfs://hadoop:9000/class6/out3
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q3DeptEarliestEmp.jar Q3DeptEarliestEmp  hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out3
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out3 目录。

hadoop fs -ls /class6/out3
hadoop fs -cat /class6/out3/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

ACCOUNTING    The earliest emp of dept:CLARK, Enter date:1981-06-09
RESEARCH    The earliest emp of dept:SMITH, Enter date:1980-12-17
SALES    The earliest emp of dept:ALLEN, Enter date:1981-02-20
请详细分析每一句话。


好的，让我来解释一下每一句话的含义：

1. 运行 Q3DeptEarliestEmp 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径路径需要全路径，否则运行会报错：

这句话的意思是运行 Q3DeptEarliestEmp 程序时需要输入三个参数，别是部门数据路径、员工数据路径和输出路径。需要注意的是，hdfs 的路径参数路径需要使用全路径，否则会导致运行错误。

2. 部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率

这句话的意思是部门数据的路径是 hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，这样可以提高处理的效率。

3. 员工数据路径：hdfs://hadoop:9000/class6/input/emp

这句话的意思是员工数据的是 hdfs://hadoop:9000/class6/input/emp。

4. 输出路径：hdfs://hadoop:9000/class6/out3

这句话的意思是输出路径是 hdfs://hadoop:9000/class6/out3。

5. cd /app/hadoop-1.1.2

这句话的意思是切换工作目录到 /app/hadoop-1.1.2 目录下。

6. hadoop jar Q3DeptEarliestEmp.jar Q3DeptEarliestEmp  hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out3

这句话的思是使用 hadoop 命令运行 Q3DeptEarliestEmp.jar 文件，并传入三个参数：部门数据路径、员工数据路径和输出路径。

7. hadoop fs -ls /class6/out3

这句话的意思是使用 hadoop fs 命令查看 /6/out3 目录下的文件列表。

8. hadoop fs -cat /class6/out3/part-r-00000

这句话的意思是使用 hadoop fs 命令查看 /class6/out3/part-r-00000 文件的内容。





17.
问题分析

求各个城市员工的总工资，需要得到各个城市所有员工的工资，通过对各个城市所有员工工资求和得到总工资。首先和测试例子 1 类似在 Mapper 的 Setup 阶段缓存部门对应所在城市数据，然后在 Mapper 阶段抽取出 key 为城市名称（利用缓存数据把部门编号对应为所在城市名称），value 为员工工资，接着在 Shuffle 阶段把传过来的数据处理为城市名称对应该城市所有员工工资，最后在 Reduce 中按照城市归组，遍历城市所有员工，求出工资总数并输出。
请结合例子详细分析一下。

这是一个求各个城市员工总工资的问题，需要对各个城市所有员工的工资进行求和。为了实现这个目标，我们可以采用 MapReduce 模型来处理数据。

首先 Mapper 的 Setup 阶段，我们可以缓存部门对应所在城市的数据。然后，在 Mapper 阶段，我们可以抽取出 key 为城市名称，value 为员工工资的数据。利用缓存数据，我们可以把部门编号对应为所在城市名称。

接着，在 Shuffle 阶段，我们可以把传过来的数据处理为城市名称对应该城市所有员工工资的形式。最后，在 Reduce 阶段，我们可以按照城市归组，遍历城市所有员工，求出工资总数输出。

例如，对于测试例子 1，我们可以得到以下数据：

Mapper 阶段输出：

| Key | Value |
| --- | --- |
| Beijing | 10000 |
| Beijing | 20000 |
| Shanghai | 15000 |
| Shanghai | 25000 |
| Guangzhou | 12000 |
| Guangzhou | 18000 |

Shuffle 阶段输出：

| Key | Value |
| --- | --- |
| Beijing | [10000, 20000] |
| Shanghai | [15000, 25000] |
| Guangzhou | [12000, 18000] |

Reduce 阶段输出：

| Key | Value |
| --- | --- |
| Beijing | 30000 |
| Shanghai | 40000 |
| Guangzhou | 30000 |

最终，我们得到了各个城市员工的总工资。






18.
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q4SumCitySalary extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {

        // 用于缓存 dept文件中的数据
        private Map<String, String> deptMap = new HashMap<String, String>();
        private String[] kv;

        // 此方法会在Map方法执行之前执行且执行一次
        @Override
        protected void setup(Context context) throws IOException, InterruptedException {
            BufferedReader in = null;
            try {
                // 从当前作业中获取要缓存的文件
                Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
                String deptIdName = null;
                for (Path path : paths) {
                    if (path.toString().contains("dept")) {
                        in = new BufferedReader(new FileReader(path.toString()));
                        while (null != (deptIdName = in.readLine())) {

                            // 对部门文件字段进行拆分并缓存到deptMap中
                            // 其中Map中key为部门编号，value为所在城市名称
                            deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[2]);
                        }
                    }
                }
            } catch (IOException e) {
                e.printStackTrace();
            } finally {
                try {
                    if (in != null) {
                        in.close();
                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            kv = value.toString().split(",");

            // map join: 在map阶段过滤掉不需要的数据，输出key为城市名称和value为员工工资
            if (deptMap.containsKey(kv[7])) {
                if (null != kv[5] && !"".equals(kv[5].toString())) {
                    context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[5].trim()));
                }
            }
        }
    }

    public static class Reduce extends Reducer<Text, Text, Text, LongWritable> {

        public void reduce(Text key, Iterable<Text> values, Context context) throws IOException,         InterruptedException {

            // 对同一城市的员工工资进行求和
            long sumSalary = 0;
            for (Text val : values) {
                sumSalary += Long.parseLong(val.toString());
            }

            // 输出key为城市名称和value为该城市工资总和
            context.write(key, new LongWritable(sumSalary));
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q4SumCitySalary");
        job.setJobName("Q4SumCitySalary");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q4SumCitySalary.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为缓存的部门数据路径、第2个参数为员工数据路径和第3个参数为输出路径
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
        FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q4SumCitySalary(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。


好的，我会逐行解释每一句代码的作用。

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
```
这部分代码是导入所需的 Java 类库。

```java
public class Q4SumCitySalary extends Configured implements Tool {
```
这里定义了一个类 `Q4SumCitySalary`，它继承了 `Configured` 和 `Tool` 类，这两个类是 Hadoop 提供的用于配置和运行 MapReduce 作业的类。

```java
public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {
```
这里定义了一个静态内部类 `MapClass`，它继承了 `Mapper` 类，用于实现 Map 阶段的逻辑。

```java
private Map<String, String> deptMap = new HashMap<String, String>();
private String[] kv;
```
这里定义了一个 `deptMap` 变量，它是一个 `Map` 类型的变量，用于缓存部门数据。另外，定义了一个 `kv` 数组，用于存储员工数据的字段。

```java
@Override
protected void setup(Context context) throws IOException, InterruptedException {
    BufferedReader in = null;
    try {
        Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
        String deptIdName = null;
        for (Path path : paths) {
            if (path.toString().contains("dept")) {
                in = new BufferedReader(new FileReader(path.toString()));
                while (null != (deptIdName = in.readLine())) {
                    deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[2]);
                }
            }
        }
    } catch (IOException e) {
        e.printStackTrace();
    } finally {
        try {
            if (in != null) {
                in.close();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
这里是 `MapClass` 类中的 `setup` 方法，它会在 Map 阶段执行之前执行一次。在这个方法中，我们可以从 DistributedCache 中获取缓存的部门数据，并将其存储到 `deptMap` 变量中。

```java
public void map(LongWritable key, Text value, Context context throws IOException, InterruptedException {
    kv = value.toString().split(",");
    if (deptMap.containsKey(kv[7])) {
        if (null != kv[5] && !"".equals(kv[5].toString())) {
            context.write(new Text(deptMap.get(kv[7].trim())), new Text(kv[5].trim()));
        }
    }
}
```
这里是 `MapClass` 类中的 `map` 方法，它实现了 Map 阶段的逻辑。在这个方法中，我们首先将员工数据的字段存储到 `kv` 数组中，然后判断该员工在的部门是否在 `deptMap` 中，如果在，则将该员工的工资和所在城市名称作为 Map 的输出。

```java
 static class Reduce extends Reducer<Text, Text, Text, LongWritable> {
    public void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
        long sumSalary = 0;
        for (Text val : values) {
            sumSalary += Long.parseLong(val.toString());
        }
        context.write(key, new LongWritable(sumSalary));
    }
}
```
这里定义了一个静态内部类 `Reduce`，它继承了 `Reducer` 类，用于实现 Reduce 阶段的逻辑。在这个类中，我们将同一城市的员工工进行求和，并将城市名称和工资总和作为 Reduce 的输出。

```java
@Override
public int run(String[] args) throws Exception {
    Job job = new Job(getConf(), "Q4SumCitySalary");
    job.setJobName("Q4SumCitySalary");
    job.setJarByClass(Q4SumCitySalary.class);
    job.setMapperClass(MapClass.class);
    job.setReducerClass(Reduce.class);
    job.setInputFormatClass(TextInputFormat.class);
    job.setOutputFormatClass(TextOutputFormat.class);
    job.setOutputKeyClass(Text.class);
    job.setOutputValueClass(Text.class);
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
    FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
    FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));
    job.waitForCompletion(true);
    return job.isSuccessful() ? 0 : 1;
}
```
这里是 `Q4SumCitySalary` 类中的 `run` 方法，它用于配置和运行 MapReduce 作业。在这个方法中，我们首先实例化一个 `Job` 对象，并设置作业名称、Jar 包、Mapper 和 Reduce 类、输入格式、输出格式、输出键值类型等参数。然后，我们从命令行参数中获取门数据路径、员工数据路径和输出路径，并将部门数据路径添加到 DistributedCache 中。最后，我们等待作业完成并返回作业执行结果。

```java
public static void main(String[] args) throws Exception {
    int res = ToolRunner.run(new Configuration(), new Q4SumCitySalary(), args);
    System.exit(res);
}
```
这里是 `Q4SumCitySalary` 类的 `main` 方法，它用于启动 MapReduce 作业。在个方法中，我们使用 `ToolRunner` 类来运行 `Q4SumCitySalary` 类，并将命令行参数传递给 `run` 方法。最后，我们退出程序并返回作业执行结果。







19.
编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q4SumCitySalary.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q4SumCitySalary.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q4SumCitySalary.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q4SumCitySalary.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q4SumCitySalary.jar ./Q4SumCity*.class
mv *.jar ../..
rm Q4SumCity*.class
请详细分析每一句话。


好的，我会逐行解释每一句代码的作用。

```bash
cd /app/hadoop-1.1.2/myclass/class6
vi Q4SumCitySalary.java
```
里进入 `/app/hadoop-1.1.2/myclass/class6` 目录，并使用 `vi` 命令创建一个名为 `Q4SumCitySalary.java` 的文件，用于编写 MapReduce 作业的代码。

```bash
javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q4SumCitySalary.java
```
这里使用 `javac` 命令编译 `Q4SumCitySalary.java` 文件，并使用 `-classpath` 参数指定编译时需要使用的类路径，其中 `../../hadoop-core-1.1.2.jar` 和 `../../lib/commons-cli-1.2.jar` 分别是 Hadoop 核心库和 Commons CLI 库的路径。

```bash
jar cvf ./Q4SumCitySalary.jar ./Q4SumCity*.class
```
这里使用 `jar` 命令将编译好的 `.class` 文件打包成一个名为 `Q4CitySalary.jar` 的 JAR 包，并将其存储到当前目录下。其中，`./Q4SumCity*.class` 表示将以 `Q4SumCity` 开头的所有 `.class` 文件都打包进 JAR 包中。

```bash
mv *.jar ../..
rm Q4SumCity*.class
```
这里使用 `mv` 命令将打包好的 JAR 包移动到 `/app/hadoop-1.1.2` 目录下，并使用 `rm` 命令删除编译好的 `.class` 文件。







20.
运行并查看结果

运行 Q4SumCitySalary 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率。
员工数据路径：hdfs://hadoop:9000/class6/input/emp。
输出路径：hdfs://hadoop:9000/class6/out4。
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q4SumCitySalary.jar Q4SumCitySalary hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out4
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out4 目录。

hadoop fs -ls /class6/out4
hadoop fs -cat /class6/out4/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

CHICAGO    9400
DALLAS    6775
NEW YORK    8750

请详细分析一下每一句话。



好的，我会逐行解释每一句代码的作用。

```bash
cd /app/hadoop-1.1.2
```
这里进入 `/app/hadoop-1.1.2` 目录，用于运行 MapReduce 作业。

```bash
hadoop jar QSumCitySalary.jar Q4SumCitySalary hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out4
```
这里使用 `hadoop jar` 命令来运行 MapReduce 作业，其中 `Q4SumCitySalary.jar` 是打包好的 JAR 包，`4SumCitySalary` 是作业的主类，后面三个参数分别是部门数据路径、员工数据路径和输出路径。在运行作业之前，需要确保 Hadoop 集群已经动。

```bash
hadoop fs -ls /class6/out4
```
这里使用 `hadoop fs -ls`令来查看 HDFS 中 `/6/out4` 目录下的文件列表。

```bash
hadoop fs -cat /class6/out4/part-r-00000
```
这里使用 `hadoop fs -cat` 命令来查看 HDFS 中class6/out4/part-r-00000` 文件的内容，也就是 MapReduce 作业的输出结果。






21.
问题分析

求工资比上司高的员工姓名及工资，需要得到上司工资及上司所有下属员工，通过比较他们工资高低得到比上司工资高的员工。在 Mapper 阶段输出经理数据和员工对应经理表数据，其中经理数据 key 为员工编号、value 为"M，该员工工资"，员工对应经理表数据 key 为经理编号、value 为"E，该员工姓名，该员工工资"。然后在 Shuffle 阶段把传过来的经理数据和员工对应经理表数据进行归组，如编号为 7698 员工，value 中标志 M 为自己工资，value 中标志 E 为其下属姓名及工资。最后在 Reduce 中遍历比较员工与经理工资高低，输出工资高于经理的员工。

请详细分析一下。
    
这是一个数据处理的问题，需要进行 MapReduce 操作。首先，在 Mapper 阶段，我们需要输出经理数据和员工对应经理表数据。经理数据的 key 为员编号，value 为"M，该员工工资"，表示该员工是经理，同时记录了该员工的工资。员工对应经表数据的 key 为经理编号，value 为"E，该员工姓名，该员工工资"，表示该员工是下属，同时记录该下属的姓名和工资。

然后，在 Shuffle 阶段，我们需要把传过来的经理数据和员工对应经理表数据进行归组，以便在 Reduce 阶段进行处理。具体来说，我们需要按照员工编号将经理数据和员工对应经理表数据进行归组，这样就可以将每个员工的经理数据和下属数据放在一起。

最后，在 Reduce 阶段，我们需要遍历每个员工的经理数据和下属数据，比较他们的工资高低，如果下属的工资高于经理的工资，则输出该下属的姓名和工资。这样就可以得到工资比上司高的员工姓名及工资。

总的来说，这个问题需要进行 Map 操作，包括 Mapper、Shuffle 和 Reduce 三个阶段。在 Mapper 阶段，我们需要输出经理数据和员工对应经理表数据；在 Shuffle 阶段，我们需要将它们进行归组；在 Reduce 阶段，我们需要遍历每个员工的经理数据和下属数据，比他们的工资高低，输出工资高于经理的员工。







22.
import java.io.IOException;
import java.util.HashMap;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q5EarnMoreThanManager extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            String[] kv = value.toString().split(",");

            // 输出经理表数据，其中key为员工编号和value为M+该员工工资
            context.write(new Text(kv[0].toString()), new Text("M," + kv[5]));

            // 输出员工对应经理表数据，其中key为经理编号和value为(E，该员工姓名，该员工工资)
            if (null != kv[3] && !"".equals(kv[3].toString())) {
                context.write(new Text(kv[3].toString()), new Text("E," + kv[1] + "," + kv[5]));
            }
        }
    }

    public static class Reduce extends Reducer<Text, Text, Text, Text> {

        public void reduce(Text key, Iterable<Text> values, Context context) throws IOException,         InterruptedException {

            // 定义员工姓名、工资和存放部门员工Map
            String empName;
            long empSalary = 0;
            HashMap<String, Long> empMap = new HashMap<String, Long>();

            // 定义经理工资变量
            long mgrSalary = 0;

            for (Text val : values) {
                if (val.toString().startsWith("E")) {
                    // 当是员工标示时，获取该员工对应的姓名和工资并放入Map中
                    empName = val.toString().split(",")[1];
                    empSalary = Long.parseLong(val.toString().split(",")[2]);
                    empMap.put(empName, empSalary);
                } else {
                    // 当时经理标志时，获取该经理工资
                    mgrSalary = Long.parseLong(val.toString().split(",")[1]);
                }
            }

            // 遍历该经理下属，比较员工与经理工资高低，输出工资高于经理的员工
            for (java.util.Map.Entry<String, Long> entry : empMap.entrySet()) {
                if (entry.getValue() > mgrSalary) {
                    context.write(new Text(entry.getKey()), new Text("" + entry.getValue()));
                }
            }
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q5EarnMoreThanManager");
        job.setJobName("Q5EarnMoreThanManager");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q5EarnMoreThanManager.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为员工数据路径和第2个参数为输出路径
String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
        FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q5EarnMoreThanManager(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。
    
    
    好的，我会逐行解释这段代码的含义和作用。

```java
import java.io.IOException;
import java.util.HashMap;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
```
这部分代码是导入所需的 Java 类库。

```java
public class Q5EarnMoreThanManager extends Configured implements Tool {
```
这里定义了一个名为 Q5EarnMoreThanManager 的类，它继承了 Configured 类并实现了 Tool 接口。

```java
public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {
```
这里定义了一个名为 MapClass 的静态内部类，它继承了 Mapper 类，并指定了 Mapper 的输入键、输入值、输出键和输出值的类型。

```java
public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
```
这里定义了一个名为 map 的方法，它重写了 Mapper 类中的 map 方法。它的参数包括输入键、输入值和上下文对象，它的作用是将输入的员工数据进行拆分，并输出经理数据和员工对应经理表数据。

```java
String[] kv = value.toString().split(",");
```
这里将输入的员工数据按逗号进行拆分，并将结果存储在一个字符串数组中。

```java
context.write(new Text(kv[0].toString()), new Text("M," + kv[5]));
```
这里输出经理数据，其中 key为员工编号，value 为"M，该员工工资"，表示该员工是经理，同时记录了该员工的工资。

```java
context.write(new Text(kv[3].toString()), new Text("E," + kv[1] + "," + kv[5]));
```
这里输出员工对应经理表数据，其中 key 为经理编号， 为"E，该员工姓名，该员工工资"，表示该员工是下属，同时记录该下属的姓名和工资。

```java
public static class Reduce extends Reducer<Text, Text, Text, Text> {
```
这里定义了一个名为 Reduce 的静态内部类，它继承了 Reducer 类，并指定了 Reducer 的输入键、输入值、输出键和输出值的类型。

```java
public void reduce(Text key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
```
这里定义了一个名为 reduce 的方法，它重写了 Reducer 类中的 reduce 方法。它的参数包括输入键、输入值和上下文对象，它的作用是遍历每个员工的经理数据和下属数据，比较他们的工资高低，如果下属的工资高于经理的工资，则输出该下属的姓名和工资。

```java
String empName;
long empSalary = 0;
HashMap<String, Long> empMap = new HashMap<String, Long>();
```
这里定义了三个变量，分别表示员工姓名、工资和存放部门员工的 HashMap。

```java
long mgrSalary = 0;
```
这里定义了一个变量，表示经理的工资。

```java
for (Text val : values) {
    if (val.toString().startsWith("E")) {
        empName = val.toString().split(",")[1];
        empSalary = Long.parseLong(val.toString().split(",")[2]);
        empMap.put(empName, empSalary);
    } else {
        mgrSalary = Long.parseLong(val.toString().split(",")[1]);
    }
}
```
这里遍历输入的值，如果是员工数据，则将员工姓名和工资存入 HashMap 中；如果是经理数据，则将经理的工资存入 mgrSalary 变量中。

```java
for (java.util.Map.Entry<String, Long> entry : empMap.entrySet()) {
    if (entry.getValue() > mgrSalary) {
        context.write(new Text(entry.getKey()), new Text("" + entry.getValue()));
    }
}
```
这里遍历 HashMap 中的员工数据，比较员工与经理工资高低，输出工资高于经理的员工。

```java
@Override
public int run(String args) throws Exception {
```
这里重写了 Tool 接口中的 run 方法。

```java
Job job = new Job(getConf(), "Q5EarnMoreThanManager");
job.setJobName("Q5EarnMoreThanManager");
```
这里创建了一个 Job 对象，并设置了作业名称。

```java
job.setJarByClass(Q5EarnMoreThanManager.class);
job.setMapperClass(MapClass.class);
job.setReducerClass(Reduce.class);
```
这里设置了 Mapper 和 Reducer 类。

```java
job.setInputFormatClass(TextInputFormat.class);
job.setOutputFormatClass(TextOutputFormat.class);
job.setOutputKeyClass(Text.class);
job.setOutputValueClass(Text.class);
```
这里设置了输入格式、输出格式、输出键和输出值的类型。

```java
String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));
```
这里设置了输入路径和输出路径。

```java
job.waitForCompletion(true);
return job.isSuccessful() ? 0 : 1;
```
这里提交作业并返回作业执行结果。

```java
public static void main(String[] args) throws Exception {
    int res = ToolRunner.run(new Configuration(), new Q5EarnMoreThanManager(), args);
    System.exit(res);
}
```
这里定义了一个 main 方法，它调用 ToolRunner 类的 run 方法来运行作业。







23.

编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q5EarnMoreThanManager.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q5EarnMoreThanManager.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q5EarnMoreThanManager.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q5EarnMoreThanManager.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q5EarnMoreThanManager.jar ./Q5EarnMore*.class
mv *.jar ../..
rm Q5EarnMore*.class
请详细分析一下每一句话。
    
    
    好的，我会逐行解释这段代码的含义和作用。

```bash
cd /app/hadoop-1.1.2/myclass/class6
```
这里进入指定目录。

```bash
vi Q5EarnMoreThanManager.java
```
这里使用 vi 编辑器打开 QEarnMoreThanManager.java 文件。

```bash
javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q5EarnMoreThanManager.java
```
这里使用 javac 命令编译 Q5EarnMoreThanManager.java 文件，并指定了类路径，其中 ../../hadoop-core-1.1.2.jar 是 Hadoop 核心库的路径，../../lib/commons-cli-1.2.jar 是 commons-cli 库的路径。

```bash
jar cvf ./Q5EarnMoreThanManager.jar ./Q5EarnMore*.
```
这里使用 jar 命令将编译好的 Q5EarnMoreThanManager.class 文件打包成 Q5EarnMoreThanManager.jar 文件，其中 cvf 参数表示创建、打包和指定文件名，./Q5EarnMoreThanManager.jar 表示打包的文件名，./Q5EarnMore*.class 表示要打包的文件名，* 通配符表示所有以 Q5EarnMore 开头的 class 文件。

```bash
mv *.jar ../..
```
这里将打包好 jar 文件移动到上一级目录。

```bash
rm Q5EarnMore*.class
```
这里删除编译好的 class 文件，以免占用过多磁盘空间。
    
    
    






24.

运行并查看结果

运行 Q5EarnMoreThanManager 运行的员工数据路径和输出路径两个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

员工数据路径：hdfs://hadoop:9000/class6/input/emp。
输出路径：hdfs://hadoop:9000/class6/out5。
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q5EarnMoreThanManager.jar Q5EarnMoreThanManager hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out5
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out5 目录。

hadoop fs -ls /class6/out5
hadoop fs -cat /class6/out5/part-r-00000
copy
打开 part-r-00000 文件，可以看到运行结果：

FORD    3000

请详细分析一下每一句话。

    
    
    好的，我会逐行解释这段代码的含义和作用。

```bash
cd /app/hadoop-1.1.2
```
这里进入指定目录。

```bash
hadoop jar Q5EarnMoreThanManager.jar Q5EarnMoreThanManagerdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out5
```
这里使用 hadoop 命令来运行 Q5EarnMoreThanManager.jar 文件，其中 Q5EarnMoreThanManager 是程序的主类名，hdfs://hadoop:9000/class6/input/emp 是输入路径，hdfs://hadoop:9000/class6/out5 是输出路径。

```bash
hadoop fs -ls /class6/out5
```
这里使用 hadoop fs 命令来查看输出路径 /class6/out5 中的文件列表。

```bash
h fs -cat /class6/out5/part-r-00000
```
这里使用 hadoop fs 命令来查看输出路径 /class6/out5 中的 part-r-00000 文件的内容，即程序的输出结果。






25.
问题分析

求工资比公司平均工资要高的员工姓名及工资，需要得到公司的平均工资和所有员工工资，通过比较得出工资比平均工资高的员工姓名及工资。这个问题可以分两个作业进行解决，先求出公司的平均工资，然后与所有员工进行比较得到结果。也可以在一个作业进行解决，这里就得使用作业 setNumReduceTasks 方法，设置 Reduce 任务数为 1，保证每次运行一个 reduce 任务，从而能先求出平均工资，然后进行比较得出结果。

在 Mapper 阶段输出两份所有员工数据，其中一份 key 为 0、value 为该员工工资，另外一份 key 为 0、value 为"该员工姓名，员工工资"。然后在 Shuffle 阶段把传过来数据按照 key 进行归组，在该任务中有 key 值为 0 和 1 两组数据。最后在 Reduce 中对 key 值 0 的所有员工求工资总数和员工数，获得平均工资。对 key 值 1，比较员工与平均工资的大小，输出比平均工资高的员工和对应的工资。
请详细分析一下。
    
    这是一个典型的 MapReduce 问题，需要使用 Hadoop 或其他分布式计算框架进行处理。该问题需要分两个阶段进行解决，第一阶段是求出公司的平均工资，第二阶段是比较每个工的工资与平均工资的大小，输出工资比平均工资高的员工姓名及工资。

在 Mapper 阶段，需要输出两数据，一份是 key 为 0、value 为该员工工资，另一份是 key 为 0、value 为"该员工姓名，员工工资"。这样可以在 Shuffle 阶段将数据按照 key 进行归组，方便在 Reduce 阶段进行处理。

在 Shuffle 阶段，传过来的数据会按照 key 进行归组，这里有两组数据，key 值为 0 和 1。对于 key 值为 0 的数据，需要对所有员工的工资进行求和，并统计员工数，从而得到公司的平均工资。对于 key 值为 1 的数据，需要比较员工的工资与平均工资的大小，输出工资比平均工资高的员工姓名及工资。

了保证每次运行一个 reduce 任务，可以使用 setNumReduceTasks 方法，设置 Reduce 任务数为 1。这样可以保证先求出均工资，然后再进行比较得出结果。

总之，该问题需要使用 MapReduce 模型进行处理，分两个阶段进行解决，需要在 Mapper 阶段输出两份数据，在 Shuffle 阶段按照 key 进行归组，在 Reduce 阶段对 key 值为 0 的数据求出平均工资，在对 key 值为 1 的数据进行比较，输出工资比平均工资高的员工姓名及工资。







26.

import java.io.IOException;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q6HigherThanAveSalary extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            String[] kv = value.toString().split(",");

            // 获取所有员工数据，其中key为0和value为该员工工资
            context.write(new IntWritable(0), new Text(kv[5]));

            // 获取所有员工数据，其中key为0和value为(该员工姓名 ,员工工资)
            context.write(new IntWritable(1), new Text(kv[1] + "," + kv[5]));
        }
    }

    public static class Reduce extends Reducer<IntWritable, Text, Text, Text> {

        // 定义员工工资、员工数和平均工资
        private long allSalary = 0;
        private int allEmpCount = 0;
        private long aveSalary = 0;

        // 定义员工工资变量
        private long empSalary = 0;

        public void reduce(IntWritable key, Iterable<Text> values, Context context) throws         IOException, InterruptedException {

            for (Text val : values) {
                if (0 == key.get()) {
                    // 获取所有员工工资和员工数
                    allSalary += Long.parseLong(val.toString());
                    allEmpCount++;
                    System.out.println("allEmpCount = " + allEmpCount);
                } else if (1 == key.get()) {
                    if (aveSalary == 0) {
                        aveSalary = allSalary / allEmpCount;
                        context.write(new Text("Average Salary = "), new Text("" + aveSalary));
                        context.write(new Text("Following employees have salarys higher than                         Average:"), new Text(""));
                    }

                    // 获取员工的平均工资
                    System.out.println("Employee salary = " + val.toString());
                    aveSalary = allSalary / allEmpCount;

                    // 比较员工与平均工资的大小，输出比平均工资高的员工和对应的工资
                    empSalary = Long.parseLong(val.toString().split(",")[1]);
                    if (empSalary > aveSalary) {
                        context.write(new Text(val.toString().split(",")[0]), new Text("" +                         empSalary));
                    }
                }
            }
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q6HigherThanAveSalary");
        job.setJobName("Q6HigherThanAveSalary");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q6HigherThanAveSalary.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 必须设置Reduce任务数为1 # -D mapred.reduce.tasks = 1
        // 这是该作业设置的核心，这样才能够保证各reduce是串行的
        job.setNumReduceTasks(1);

        // 设置输出格式类
        job.setMapOutputKeyClass(IntWritable.class);
        job.setMapOutputValueClass(Text.class);

        // 设置输出键和值类型
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(LongWritable.class);

        // 第1个参数为员工数据路径和第2个参数为输出路径
String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
        FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q6HigherThanAveSalary(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。
    
    
    好的，我会逐行解释每一句代码的作用。

```java
import java.io.IOException;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
```

这部分代码是导入所需的 Java 类库。

```java
public class Q6HigherThanAveSalary extends Configured implements Tool {
```

这里定义了一个名为 Q6HigherThanAveSalary 的类，该类继承了 Configured 类并实现了 Tool 接口。

```java
public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {
```

这里定义了一个名为 MapClass 的静态内部类，该类继承了 Mapper 类，并指定了输入键、输入值、输出键和输出值的类型。

```java
public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
```

这里定义了一个名为 map 的方法，该方法是 Mapper 类的一个抽象方法，需要在子类中现。该方法的作用是将输入数据转换为键值对。

```java
String[] kv = value.toString().split(",");
```

这里将输入的文本数据按照逗号进行拆分，得到一个字符串数组。

```java
context.write(new IntWritable(0), new Text(kv[5]));
```

这里将员工工资作为 value，key 为 0，输出到 Reduce 阶段。

```java
context.write(new IntWritable(1), new Text(kv[1] + "," + kv[5]));
```

这里将员工姓名和工资作为 value，key 为 1，输出到 Reduce 阶段。

```java
public static class Reduce extends Reducer<IntWritable, Text, Text, Text> {
```

这里定义了一个名为 Reduce 的静态内部类，该类继承了 Reducer 类，并指定了输入键、输入值、输出键和输出值的类型。

```java
private long allSalary = 0;
private int allEmpCount = 0;
private long aveSalary = 0;
private long empSalary = 0;
```

这里定义了一些变量，于存储员工工资、员工数和平均工资等信息。

```java
public void reduce(IntWritable key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
```

这里定义了一个名为 reduce 的方法，该方法是 Reducer 类的一个抽象方法，需要在子类中实现。该方法的作用是将 Mapper段输出的键值对进行合并和处理。

```java
for (Text val : values) {
```

这里使用 for 循环遍历 values，values 是一个 Iterable 类型的对象，包含了 Mapper 阶段输出的所有 value。

```java
if (0 == key.get()) {
    allSalary += Long.parseLong(val.toString());
   EmpCount++;
}
```

这里判断 key 是否为 0，如果是，则将员工工资累加到 allSalary 变量中，并将员工数加 1。

```java
else if (1 == key.get()) {
    if (aveSalary == ) {
        aveSalary = allSalary / allEmpCount;
        context.write(new Text("Average Salary = "), new Text("" + aveSalary));
        context.write(new Text("Following employees have salarys higher than Average:"), new Text(""));
    }
    empSalary = Long.parseLong(val.toString().split(",")[1]);
    if (empSalary > aveSalary) {
        context.write(new Text(val.toString().split(",")[0]), new Text("" + empSalary));
    }
}
```

这里判断 key 是否为 1，如果是，则计算平均工资，并比较员工工资与平均工资的大小，输出工资平均工资高的员工姓名及工资。

```java
@Override
public int run(String[] args) throws Exception {
```

这里重写了 Tool 接口中的 run 方法，该方法是程序的入口。

```java
Job job = new Job(getConf(), "Q6HigherThanAveSalary");
job.setJobName("Q6HigherThanAveSalary");
```

这里创建了一个 Job 对象，并设置了作业名称。

```java
job.setJarByClass(Q6HigherThanAveSalary.class);
job.setMapperClass(MapClass.class);
job.setReducerClass(Reduce.class);
```

这里设置了 Mapper 和 Reducer 类。

```java
job.setNumReduceTasks(1);
```

这里设置 Reduce 任务数为 1，保证各 reduce 是串行的。

```java
job.setMapOutputKeyClass(IntWritable.class);
job.setMapOutputValueClass(Text.class);
```

这里设置 Mapper 阶段的输出键和输出值类型。

```java
job.setOutputFormatClass(TextOutputFormat.class);
job.setOutputKeyClass(Text.class);
job.setOutputValueClass(LongWritable.class);
```

这里设置输出格式类和输出键值类型。

```java
String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));
```

这里设置输入路径和输出路径。

```java
job.waitForCompletion(true);
return job.isSuccessful() ? 0 : 1;
```

这里提交作业并等待作业完成，返回作业执行结果。






27.
编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q5EarnMoreThanManager.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q6HigherThanAveSalary.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q6HigherThanAveSalary.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q6HigherThanAveSalary.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q6HigherThanAveSalary.jar ./Q6HigherThan*.class
mv *.jar ../..
rm Q6HigherThan*.class
请详细分析一下 每一句话。
    
    好的，我会逐行解释每一句代码的作用。

```bash
cd /app/hadoop-1.1.2/myclass/class6
vi Q6HigherAveSalary.java
```

这里进入 /app/hadoop-1.1.2/myclass/class6 目录，并使用 vi 编辑器创建 Q6HigherThanAveSalary.java 文件。

```bash
javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q6HigherThanAveSalary.java
```

这里使用 javac 命令编译 Q6HigherAveSalary.java 文件，并指定类路径为 ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar。

```bash
jar cvf ./Q6HigherThanAveSalary.jar ./Q6HigherThan*.class
```

这里使用 jar 命令将编译好的 Q6HigherThanAveSalary.class 文件打包成 Q6HigherThanAveSalary.jar 文件，并指定打包的文件名和文件路径。

```bash
mv *.jar ../..
```

这里将打包好的 Q6HigherThanAveSalary.jar 文件移动到上一级目录。

```bash
rm Q6HigherThan*.class
```

这里删除编译好的 Q6HigherThanAveSalary.class 文件，以免占用过磁盘空间。








28.
    运行并查看结果

运行 Q6HigherThanAveSalary 运行的员工数据路径和输出路径两个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

员工数据路径：hdfs://hadoop:9000/class6/input/emp
输出路径：hdfs://hadoop:9000/class6/out6
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q6HigherThanAveSalary.jar Q6HigherThanAveSalary  hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out6
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out6 目录。

hadoop fs -ls /class6/out6
hadoop fs -cat /class6/out6/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

Average Salary =     2077
Following employees have salarys higher than Average:
FORD    3000
CLARK    2450
KING    5000
JONES    2975
BLAKE    2850
请详细分析一下每一句话。
    
    好的，我会逐行解释每一句代码的作用。

```bash
cd /app/hadoop-1.1.2
```

这里进入 /app/hadoop-1.1.2 目录。

```bash
hadoop jar Q6HigherThanAveSalary.jar Q6HigherThanAveSalary hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out6
```

这里使用 hadoop 命令运行 Q6HigherThanAveSalary.jar 文件，并指定运行的类为 Q6HigherThanAveSalary，同时指定输入路径和输出路径。

```bash
hadoop -ls /class6/out6
```

这里使用 hadoop fs 命令查看输出路径 /class6/out6 中的文件列表。

```bash
hadoop fs -cat /class6/out6/part-r-00000
```

这里使用 hadoop fs 命令查看输出路径 /class6/out6 中的 part-r-00000 文件的内容。








29.
问题分析

求名字以 J 开头的员工姓名机器所属部门名称，只需判断员工姓名是否以 J 开头。首先和问题 1 类似在 Mapper 的 Setup 阶段缓存部门数据，然后在 Mapper 阶段判断员工姓名是否以 J 开头，如果是抽取出员工姓名和员工所在部门编号，利用缓存部门数据把部门编号对应为部门名称，转换后输出结果。
    
    这是一个关于如何在 MapReduce 框架中实现求名字以 J 开头的员工姓名机器所属部门名称的问题分析。

首先，在 Mapper 的 Setup 阶段，可以将部门数据缓存到内存中，以便在 Mapper 阶段中使用。然后，在 Mapper 阶段，对于每个输入记录，可以判断员工姓名是否以 J 开头。如果是，就抽取出员工姓名和员工所在部门编号，并利用缓存的部门数据将部门编号对应为部门名称。最后，将转换后的结果输出。

具体实现可以参考以下步骤：

1. 在 Mapper 的 Setup 阶段，使用 DistributedCache 将部门数据缓存到内存中。可以使用以下代码实现：

```
public void setup(Context context) throws IOException, InterruptedException {
    // Get the cached department data file
    Path[] cacheFiles = DistributedCache.getLocalCacheFiles(context.getConfiguration());
    Path departmentFile = cacheFiles[0];

    // Read the department data and store it in a HashMap
    Map<String, String> departmentMap = new HashMap<String, String>();
    BufferedReader reader = new BufferedReader(new FileReader(departmentFile.toString()));
    String line;
    while ((line = reader.readLine()) != null) {
        String[] tokens = line.split(",");
        departmentMap.put(tokens[0], tokens[1]);
    }
    reader.close();

    // Store the department data in the context for later use
    context.getConfiguration().set("departmentMap", new Gson().toJson(departmentMap));
}
```

2. 在 Mapper 阶段，对于每个输入记录，判断员工姓名是否以 J 开头，并抽取出员工姓名和员工所在部门编号。然后，利用缓存的部门数据将部门编号对应为部门名称。最后，将转换后的结果输出。可以使用以下代码实现：

```
public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
    // Get the department data from the context
    Map<String, String> departmentMap = new Gson().fromJson(context.getConfiguration().get("departmentMap"), new TypeToken<Map<String, String>>(){}.getType());

    // Parse the input record
    String[] tokens = value.toString().split(",");
    String name = tokens[0];
    String departmentId = tokens[1];

    // Check if the name starts with J
    if (name.startsWith("J")) {
        // Get the department name from the departmentMap
        String departmentName = departmentMap.get(departmentId);

        // Output the result
        context.write(new Text(name), new Text(departmentName));
    }
}
```

以上就是在 MapReduce 框架中实现求名字以 J 开头的员工姓名机器属部门名称的问题分析和实现步骤。







30.
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.filecache.DistributedCache;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q7NameDeptOfStartJ extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, Text, Text> {

        // 用于缓存 dept文件中的数据
        private Map<String, String> deptMap = new HashMap<String, String>();
        private String[] kv;

        // 此方法会在Map方法执行之前执行且执行一次
        @Override
        protected void setup(Context context) throws IOException, InterruptedException {
            BufferedReader in = null;
            try {

                // 从当前作业中获取要缓存的文件
                Path[] paths = DistributedCache.getLocalCacheFiles(context.getConfiguration());
                String deptIdName = null;
                for (Path path : paths) {

                    // 对部门文件字段进行拆分并缓存到deptMap中
                    if (path.toString().contains("dept")) {
                        in = new BufferedReader(new FileReader(path.toString()));
                        while (null != (deptIdName = in.readLine())) {

                            // 对部门文件字段进行拆分并缓存到deptMap中
                            // 其中Map中key为部门编号，value为所在部门名称
                            deptMap.put(deptIdName.split(",")[0], deptIdName.split(",")[1]);
                        }
                    }
                }
            } catch (IOException e) {
                e.printStackTrace();
            } finally {
                try {
                    if (in != null) {
                        in.close();
                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            kv = value.toString().split(",");

            // 输出员工姓名为J开头的员工信息，key为员工姓名和value为员工所在部门名称
            if (kv[1].toString().trim().startsWith("J")) {
                context.write(new Text(kv[1].trim()), new Text(deptMap.get(kv[7].trim())));
            }
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q7NameDeptOfStartJ");
        job.setJobName("Q7NameDeptOfStartJ");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q7NameDeptOfStartJ.class);
        job.setMapperClass(MapClass.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为缓存的部门数据路径、第2个参数为员工数据路径和第3个参数为输出路径
String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    DistributedCache.addCacheFile(new Path(otherArgs[0]).toUri(), job.getConfiguration());
        FileInputFormat.addInputPath(job, new Path(otherArgs[1]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[2]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q7NameDeptOfStartJ(), args);
        System.exit(res);
    }
}
请详细分析每一句代码。
    
    
    







31.
编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q7NameDeptOfStartJ.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q7NameDeptOfStartJ.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q7NameDeptOfStartJ.java
编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q7NameDeptOfStartJ.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q7NameDeptOfStartJ.jar ./Q7NameDept*.class
mv *.jar ../..
rm Q7NameDept*.class
请详细分析每一句话。
    
    
    好的，我会逐行分析这段代码。

```
cd /app/hadoop-1.1.2/myclass/class6
```
这段代码使用 cd 命令进入 /app/hadoop-1.1.2/myclass6 目录。

```
vi Q7NameDeptOfStartJ.java
```
这段代码使用 vi 命令编辑 Q7NameDeptOfStartJ.java 文件。

```
javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q7NameDeptOfStartJ.java
```
这段代码使用 javac 命编译 Q7NameDeptOfStartJ.java 文件，并使用 -classpath 参数指定编译时需要的类路径。其中，../../hadoop-core-1.1.2.jar 和 ../../lib/commons-cli-1.2.jar 分别是adoop 核心库和 commons-cli 库的路径。

```
jar cvf ./Q7NameDeptOfStartJ.jar ./Q7NameDept*.class
```
这段代码使用 jar 命令将编译好的 Q7NameDeptOfStartJ.class 文件打包成 Q7NameDeptOfStartJ.jar 文件。其中，-cvf 参数表示新的 jar 文件并将文件添加到其中，./Q7NameDeptOfStartJ.jar 表示指定打包后的文件名和路径，./Q7NameDept*.class 表示指定要打包的文件名和路径，* 号表示通配符，表示所有以 Q7NameDept 开头的 .class 文件都会被打包。

```
mv *.jar ../..
```
这段代码使用 mv 命令将打包好的 Q7NameDeptOfStartJ.jar 文件移动到 /app/hadoop-1.1.2 目录下。

```
rm Q7NameDept*.class
```
这段代码使用 rm 命令删除编译好的 Q7NameDeptOfStartJ.class 文件。








32.
运行并查看结果

运行 Q7NameDeptOfStartJ 时需要输入部门数据路径、员工数据路径和输出路径三个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

部门数据路径：hdfs://hadoop:9000/class6/input/dept，部门数据将缓存在各运行任务的节点内容中，可以提高处理的效率。
员工数据路径：hdfs://hadoop:9000/class6/input/emp。
输出路径：hdfs://hadoop:9000/class6/out7。
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q7NameDeptOfStartJ.jar Q7NameDeptOfStartJ hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out7
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out7 目录。

hadoop fs -ls /class6/out7
hadoop fs -cat /class6/out7/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

JAMES    SALES
JONES    RESEARCH
请详细分析每一句话。

    好的，我会逐行分析这段代码。

```
cd /app/hadoop-1.1.2
```
这段代码使用 cd 命令进入 //hadoop-1.1.2 目录。

```
hadoop jar Q7NameDeptOfStartJ.jar Q7NameDeptOfStartJ hdfs://hadoop:9000/class6/input/dept hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out7
```
这段代码使用 hadoop 命令运行 Q7NameDeptOfStartJ 作业，并指定部门数据路径、员工数据路径和输出路径三个参数。其中，hadoop jar 表示运行 Hadoop 作业Q7NameDeptOfStartJ.jar 表示要运行的作业 jar 包，Q7NameDeptOfStartJ 表示要运行的作业类，hdfs://hadoop:9000/class6/input/dept 表示部门数据路径，hdfs://hadoop:0/class6/input/emp 表示员工数据路径，hdfs://hadoop:9000/class6/out7 表示输出路径。

```
hadoop fs -ls /class6/out7
```
这段代码使用 hadoop fs 命令查看 /class6/out7 目录的文件列表。

```
hadoop fs -cat /class6/out7/part-r-00000
```
这段代码使用 hadoop fs 命令查看 /class6/out7/part-r-00000 文件的内容。其中，-cat 参数表示查看文件内容。







33.
问题分析

求工资最高的头三名员工姓名及工资，可以通过冒泡法得到。在 Mapper 阶段输出经理数据和员工对应经理表数据，其中经理数据 key 为 0 值、value 为"员工姓名，员工工资"。最后在 Reduce 中通过冒泡法遍历所有员工，比较员工工资多少，求出前三名。

请详细分析一下。
    
    这段文本描述了一个数据处理的流程，主要是针对求工资最高的头三名员工姓名及工资这个问题进行分析和解决。下面是对这个流程的详细分析：

1. 冒泡法：冒泡法是一种简单的排序算法，它的基本思想是通过相邻元素之间的比较和交换来实现排序。在这个流程中，冒泡法被用来对所有员工的工资进行排序，以便找出工资最高的前三名员工。

2. Mapper 阶段：在 Mapper 阶段，数据被分成多个小块，每个小块都由一个 Mapper 处理。在这个流程中，Mapper 的任务是将经理数据和员工对应经理表数据输出，其中经理数据的 key 值为 0，value 值为"员工，员工工资"。这个过程可以通过编写 Map 函数来实现。

3. Reduce 阶段：在 Reduce 阶段，所有 Mapper 输出的数据合并起来，然后按照 key 值进行排序和分组。在这个流程中，Reduce 的任务是通过冒泡法遍历所有员工，比较员工工资多少，求出前三名。个过程可以通过编写 Reduce 函数来实现。

4. 数据处理流程的目标：最终的目标是找出工资最高的前名员工姓名和工资。这个目标可以通过在 Reduce 阶段对所有员工的工资进行排序和比较来实现。

总之，这个数据处理流程主要是通过冒泡法和 MapReduce 模型来实现对员工工资数据的处理和分析，以便找出工资最高的前三名员工。在这个过程中，系统工程师需要具备系统设计、集成和测试等方面的技能，同时需要具备分析问题、解决问题、沟通协作、注重细节、持续改进、风险管理、时间管理和客户满意度等方面的能力。







34.
    import java.io.IOException;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q8SalaryTop3Salary extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            String[] kv = value.toString().split(",");

            // 输出key为0和value为员工姓名+","+员工工资
            context.write(new IntWritable(0), new Text(kv[1].trim() + "," + kv[5].trim()));
        }
    }

    public static class Reduce extends Reducer<IntWritable, Text, Text, Text> {

        public void reduce(IntWritable key, Iterable<Text> values, Context context) throws         IOException, InterruptedException {

            // 定义工资前三员工姓名
            String empName;
            String firstEmpName = "";
            String secondEmpName = "";
            String thirdEmpName = "";

            // 定义工资前三工资
            long empSalary = 0;
            long firstEmpSalary = 0;
            long secondEmpSalary = 0;
            long thirdEmpSalary = 0;

            // 通过冒泡法遍历所有员工，比较员工工资多少，求出前三名
            for (Text val : values) {
                empName = val.toString().split(",")[0];
                empSalary = Long.parseLong(val.toString().split(",")[1]);

                if(empSalary > firstEmpSalary) {
                    thirdEmpName = secondEmpName;
                    thirdEmpSalary = secondEmpSalary;
                    secondEmpName = firstEmpName;
                    secondEmpSalary = firstEmpSalary;
                    firstEmpName = empName;
                    firstEmpSalary = empSalary;
                } else if (empSalary > secondEmpSalary) {
                    thirdEmpName = secondEmpName;
                    thirdEmpSalary = secondEmpSalary;
                    secondEmpName = empName;
                    secondEmpSalary = empSalary;
                } else if (empSalary > thirdEmpSalary) {
                    thirdEmpName = empName;
                    thirdEmpSalary = empSalary;
                }
            }

            // 输出工资前三名信息
            context.write(new Text( "First employee name:" + firstEmpName), new Text("Salary:"             + firstEmpSalary));
            context.write(new Text( "Second employee name:" + secondEmpName), new                     Text("Salary:" + secondEmpSalary));
            context.write(new Text( "Third employee name:" + thirdEmpName), new Text("Salary:"             + thirdEmpSalary));
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q8SalaryTop3Salary");
        job.setJobName("Q8SalaryTop3Salary");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q8SalaryTop3Salary.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);
        job.setMapOutputKeyClass(IntWritable.class);
        job.setMapOutputValueClass(Text.class);

        // 设置输入格式类
        job.setInputFormatClass(TextInputFormat.class);

        // 设置输出格式类
        job.setOutputKeyClass(Text.class);
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为员工数据路径和第2个参数为输出路径
        String[] otherArgs = new GenericOptionsParser(job.getConfiguration(),                     args).getRemainingArgs();
        FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q8SalaryTop3Salary(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。
    
    
    好的，下面是对每一句代码的详细分析：

1. `import java.io.IOException;`：导入 Java IO 异常类。

2. `import org.apache.hadoop.conf.Configuration;`：导入 Hadoop 配置类。

3. `import org.apache.hadoop.conf.Configured;`：导入 Hadoop置类的子类 Configured。

4. `import org.apache.hadoop.fs.Path;`：导入 Hadoop 文件系统路径类。

5. `import org.apache.hadoop.io.IntWritable;`：导入 Hadoop 整型可写类。

6. `import org.apache.hadoop.io.LongWritable;`：导入 Hadoop 长整型可写类。

7. `import org.apache.hadoop.io.Text;`：导入 Hadoop 文本类。

8. `import org.apache.hadoop.mapreduce.Job;`：导入adoop 作业类。

9. `import org.apache.hadoop.mapreduce.Mapper;`：导入 Hadoop Mapper 类。

10. `import org.apache.hadoop.mapreduce.Reducer;`：导入 Hadoop Reducer 类。

11. `import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;`：导入 Hadoop 文件输入格式类。

12. `import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;`：导入 Hadoop 文本输入格式类。

13. `import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;`：导入 Hadoop 文件输出格式类。

14. `import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;`：导入 Hadoop 文本输出格式类。

15. `import org.apache.hadoop.util.GenericOptionsParser;`：导入 Hadoop 通用选项解析器类。

16. `import org.apache.hadoop.util.Tool;`：导入 Hadoop 工具类。

17. `import org.apache.hadoop.util.ToolRunner;`：导入 Hadoop 工具类的运行器类。

18. `public class Q8SalaryTop3 extends Configured implements Tool {`：定义一个名为 Q8SalaryTop3Salary 的类，继承自 Configured 类并实现 Tool 接口。

19. `public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {`：定义一个名为 MapClass 的静态内部类，继承自 Mapper 类，泛型参数分别为 LongWritable、Text、IntWritable 和 Text。

20. `public void map(LongWritable key Text value, Context context) throws IOException, InterruptedException {`：重写 Mapper 类的 map 方法，参数分别为 LongWritable、Text 和 Context，抛出 IOException 和 InterruptedException 异常。

21. `String[] kv = value.toString().split(",");`：将输入的文本数据按逗号进行拆分，存储到字符串数组 kv 中。

22. `context.write(new IntWritable(), new Text(kv[1].trim() + "," + kv[5].trim()));`：将员工姓名和工资拼接成字符串，作为 value 值，key 值为 0，输出到 Reduce 阶段。

23. `public static class Reduce extends Reducer<IntWritable, Text, Text, Text {`：定义一个名为 Reduce 的静态内部类，继承自 Reducer 类，泛型参数分别为 IntWritable、Text、Text 和 Text。

24. `public void(IntWritable key, Iterable<Text> values, Context context) throws IOException, InterruptedException {`：重写 Reducer 类的 reduce 方法，参数分别为 IntWritable、Iterable<Text> 和 Context，抛出 IOException 和 InterruptedException 异常。

25. `String empName;`：定义一个字符串变量 empName，用于存储员工姓名。

26. `String firstEmpName = "";`：定义一个字符串变量 firstEmpName，用于存储工资最高的员工姓名。

27. `String secondEmpName = "";`：定义一个字符串变量 secondEmpName，用于存储工资第二高的员工姓名。

28. `String thirdEmpName = "";`：定义一个字符串变量 thirdEmpName，用于存储资第三高的员工姓名。

29. `long empSalary = 0;`：定义一个长整型变量 empSalary，用于存储员工工资。

30. `long firstEmpSalary = 0;`：定义一个长整型变量 firstEmpSalary用于存储工资最高的员工工资。

31. `long secondEmpSalary = 0;`：定义一个长整型变量 secondEmpSalary，用于存储工资第二高的员工工资。

32. `long thirdEmpSalary = 0;`：定义一个长整型变量 thirdEmpSalary，用于存储工资第三高的员工工资。

33. ` (Text val : values) {`：遍历所有员工的资数据。

34. `empName = val.toString().split(",")[0];`：将员工姓名存储到 empName 变量中。

35. `empSalary = Long.parseLong(val.toString().split(",")[1]);`：将员工工资转为长整型并存储到 empSalary 变量中。

36. `if(empSalary > firstEmpSalary) {`：如果当前员工工资大于工资最高的员工工资。

37. `thirdEmpName = secondEmpName;`：将工资第二高的员工姓名赋值工资第三高的员工姓名。

38. `thirdEmpSalary = secondEmpSalary;`：将工资第二高的员工工资赋值给工资第三高的员工工资。

39. `secondEmpName = firstEmpName;`：将工资最高的员工姓名赋值给工第二高的员工姓名。

40. `secondEmpSalary = firstEmpSalary;`：将工资最高的员工工资赋值给工资第二高的员工工资。

41. `firstEmpName = empName;`：将当前员工姓名赋值给工资最高的员姓名。

42. `firstEmpSalary = empSalary;`：将当前员工工资赋值给工最高的员工工资。

43. `} if (empSalary > secondEmpSalary) {`：如果当前员工工资大于工资第二高的员工工资。

44. `thirdEmpName = secondEmpName;`：将工资第二高的员工姓名赋给工资第三高的员工姓名。

45. `thirdEmpSalary = secondEmpSalary;`：将工资第二高的员工工资赋值给工资第三高的员工工资。

46. `secondEmpName = empName;`：将当前员工姓名赋值给工资第二高的员工姓名。

47. `secondEmpSalary = empSalary;`：将当前员工工资赋值给工资第二高的员工工资。

48. `} else if (empSalary > thirdEmpSalary) {`：如果当前员工工资大于工资第三高的员工工资。

49. `thirdEmpName = empName;`：将当前员工赋值给工资第三高的员工姓名。

50. `thirdEmpSalary = empSalary;`：将当前工工资赋值给工资第三高的员工工资。

51. `}`：结束 if-else 语句。

52. `context.write(new Text( "First employee:" + firstEmpName), new Text("Salary:" + firstEmpSalary));`：输出工资最高的员工姓名和工资。

53. `context.write(new Text( "Second employee name:" + secondEmpName), new Text("Salary:" + secondEmpSalary));`：输出资第二高的员工姓名和工资。

54. `context.write(new Text( "Third employee name:" + thirdEmpName), new Text("Salary:" + thirdEmpSalary));`：输出工资第三高的员工姓名和工资。

55. `@Override：重写 Tool 接口的 run 方法。

56. `public int run(String[] args) throws Exception {`：重写 Tool 接口的 run 方法，参数为字符串数组 args，抛出 Exception 异常。

57. `Job job = new Job(getConf(), "Q8SalaryTop3Salary");`：创建一个 Job 对象，传入 Hadoop 配置对象和作业名称。

58. `job.setJobName("Q8SalaryTop3Salary");`：设置作业名称。

59. `job.setJarByClass(Q8SalaryTop3Salary.class);`：设置作业的主类。

60. `job.setMapperClass(MapClass.class);`：设置 Mapper 类。

61. `job.setReducerClass(Reduce.class);`：设置 Reducer 类。

62. `job.setMapOutputKeyClass(IntWritable.class);`：设置 Mapper 输出的 key 类型。

63. `job.setMapOutputValueClass(Text.class);`：设置 Mapper 输出的 value 类型。

64. `job.setInputFormatClass(TextInputFormat.class);`：设置输入格式类。

65. `job.setOutputKeyClass(Text.class);`：设置输出 key 类型。

66. `job.setOutputFormatClass(TextOutputFormat.class);`：设置输出格式类。

67. `job.setOutputValueClass(Text.class);`：设置输出 value 类型。

68. `String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();`：使用通用选项解析器获取输入路径和输出路径。

69. `FileInputFormat.addInputPath(job, new Path(otherArgs[0]));`：设置输入路径。

70. `FileOutputFormatPath(job, new Path(otherArgs[1]));`：设置输出路径。

71. `job.waitForCompletion(true);`：提交作业并等待完成。

72. `return job.isSuccessful() ? 0 : 1;`：返回作业执行结果。

73. `public static void main(String[] args) throws Exception {`：主方法。

74. `int res = ToolRunner.run(new Configuration(), new Q8SalaryTop3Salary(), args);`：运行作业。

75. `System.exit(res);`：退出程序。








35.
编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q8SalaryTop3Salary.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q8SalaryTop3Salary.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q8SalaryTop3Salary.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q8SalaryTop3Salary.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q8SalaryTop3Salary.jar ./Q8SalaryTop3*.class
mv *.jar ../..
rm Q8SalaryTop3*.class

请详细分析每一句话。
    
    好的，下面是对每一句代码的详细分析：

1. `cd /app/hadoop-1.1.2/myclass/class6`：进入指定目录。

2. `vi Q8SalaryTop3Salary.java`：使用 vi 编辑打开 Q8SalaryTop3Salary.java 文件。

3. `javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q8SalaryTop3Salary.java`：使用 javac 命令编译 Q8SalaryTop3Salary.java 文件，-classpath 参数指定编译时需要的类，包括 Hadoop 核心库和 commons-cli 库。

4. `jar cvf ./Q8SalaryTop3Salary.jar ./Q8SalaryTop3*.class`：使用 jar 命令将编译好的 Q8SalaryTop3Salary 类打包成 jar 文件，-c 参数表示创建新的 jar 文件，-v 参数表示在标准输出中显示详细信息，-f 参数指定 jar 文件名，最后一个参数指定需要打包的类文件。

5. `mv *.jar ../..`：将打包好的 jar 文件移动到上一级目录。

6. `rm Q8SalaryTop3*.class`：删除编译的类文件。







36.
运行并查看结果

运行 Q8SalaryTop3Salary 运行的员工数据路径和输出路径两个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

员工数据路径：hdfs://hadoop:9000/class6/input/emp。
输出路径：hdfs://hadoop:9000/class6/out8。
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q8SalaryTop3Salary.jar Q8SalaryTop3Salary hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out8
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out8 目录。

hadoop fs -ls /class6/out8
hadoop fs -cat /class6/out8/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

First employee name:KING    Salary:5000
Second employee name:FORD    Salary:3000
Third employee name:JONES    Salary:2975

请详细分析一下每一句话。
    
    好的，下面是对每一句代码的详细分析：

1. `cd /app/hadoop-1.1.2`：进入指定目录。

2. `hadoop jar Q8SalaryTop3Salary.jar Q8SalaryTop3Salary hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out8`： hadoop 命令运行 Q8SalaryTop3Salary 类，传入员工数据路径和输出路径两个参数。

3. `hadoop fs -ls /class6/out8`：使用 hadoop fs 命令查看输出路径 /class6/out8 目录下的文件。

4. `hadoop fs -cat /class6/out8/part-r-00000`：使用 hadoop fs 命令查看输出路径 /class6/out8 目录下的 part-r-00000 文件内容。

5. 打开 part-r-00000 文件，可以看到运行结果：输出工资最高的员工姓名和工资，输出资第二高的员工姓名和工资，输出工资第三高的员工姓名和工资。







37.
问题分析

求全体员工总收入降序排列，获得所有员工总收入并降序排列即可。在 Mapper 阶段输出所有员工总工资数据，其中 key 为员工总工资、value 为员工姓名，在 Mapper 阶段的最后会先调用 job.setPartitionerClass 对数据进行分区，每个分区映射到一个 reducer，每个分区内又调用 job.setSortComparatorClass 设置的 key 比较函数类排序。由于在本作业中 Map 的 key 只有 0 值，故能实现对所有数据进行排序。
请详细分析一下。
    
    这是一个 MapReduce 任务，目的是对所有员工的总收入进行降序排列。在 Mapper 阶段，每个员工的姓名和总收入会被映射成一个键值对，其中键是员工的总收入，值是工的姓名。这些键值对会被发送到不同的 reducer 中，每个 reducer 会对它们进行排序并输出结果。

在 Mapper 阶段最后，会使用 job.setPartitionerClass 方法对数据进行分区，这意味着每个 reducer 只会接收到一部分数据。这个方法会根据键的哈希值将数据分配到不同的 reducer 中。这样做的目的是为了让每个 reducer 只处理一部分数据，从而提高处理效率。

在每个 reducer 中，会使用 job.setSortComparatorClass 方法设置一个比较函数类，用于对键进行排序。这个方法会根据键的值对键值对进行排序，从而实现对所有员工总收入的降序排列。

最终，所有 reducer 的输出会被合并成一个结果，并按照降序排列的顺序输出所有员工的总收入和姓名。这就能够得到一个按照总收入降序排列的员工列表。








38.
    import java.io.IOException;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.io.WritableComparable;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q9EmpSalarySort extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            String[] kv = value.toString().split(",");

            // 输出key为员工所有工资和value为员工姓名
            int empAllSalary = "".equals(kv[6]) ? Integer.parseInt(kv[5]) :                             Integer.parseInt(kv[5]) + Integer.parseInt(kv[6]);
            context.write(new IntWritable(empAllSalary), new Text(kv[1]));
        }
    }

    /**
     * 递减排序算法
     */
    public static class DecreaseComparator extends IntWritable.Comparator {
        public int compare(WritableComparable a, WritableComparable b) {
            return -super.compare(a, b);
        }

        public int compare(byte[] b1, int s1, int l1, byte[] b2, int s2, int l2) {
            return -super.compare(b1, s1, l1, b2, s2, l2);
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q9EmpSalarySort");
        job.setJobName("Q9EmpSalarySort");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q9EmpSalarySort.class);
        job.setMapperClass(MapClass.class);

        // 设置输出格式类
        job.setMapOutputKeyClass(IntWritable.class);
        job.setMapOutputValueClass(Text.class);
        job.setSortComparatorClass(DecreaseComparator.class);

        // 第1个参数为员工数据路径和第2个参数为输出路径
        String[] otherArgs = new GenericOptionsParser(job.getConfiguration(),                     args).getRemainingArgs();
        FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q9EmpSalarySort(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。
    
    
    这是一个使用 Hadoop MapReduce 实现对员工总收入进行降序排列的程序。下面是每一句代码的详细分析：

```java
public static class MapClass extends Mapper<LongWritable,, IntWritable, Text> {
    // Mapper 类，继承自 Hadoop 的 Mapper 类，用于将输入数据映射为键值对
    // 输入键类型为 LongWritable，输入值类型为 Text，输出键类型为 IntWritable，输出值类型为 Text
    // Mapper 类中的 map 方法会被adoop 自动调用，用于对输入数据进行处理
    // 在本例中，map 方法会将员工总收入作为键，员工姓名作为值输出
}

public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
    // Mapper 类中的 map 方法，用于对输入数据进行处理
    // key 表示输入数据的键，value 表示输入数据的值，context 表示 Mapper 的上下文
    // 在本例中，输入数据的键为文件中行号，值为文件中的一行数据
    // 对员工文件字段进行拆分
    String[] kv = value.toString().split(",");
    // 将员工基本工资和津贴相加得到员工总收入
    int empAllSalary = "".equals(kv[6]) ? Integer.parseInt(kv[5]) : Integer.parseInt(kv[5]) + Integer.parseInt(kv[6]);
    // 输出键为员工总收入，值为员工姓名
    context.write(new IntWritable(empAllSalary), new Text(kv[1]));
}

public static class DecreaseComparator extends IntWritable.Comparator {
    // 自定义的递减排序算法，继承自 Hadoop 的 IntWritable.Comparator 类
    // 在本例中，用于对 Mapper 输出的键（员工总收入）进行降序排列
    public int compare(WritableComparable a, WritableComparable b) {
        return -super.compare(a, b);
    }

    public int compare(byte[] b1, int s1, int l1, byte[] b2, int s2, int l2) {
        return -super.compare(b1, s1, l1, b2, s2, l2);
    }
}

@Override
public int run(String[] args) throws Exception {
    // 实现 Tool 接口的 run 方法，用于运行 MapReduce 作业
    // 在本例中，用于对员工总收入进行降序排列
    // 实例化作业对象，设置作业名称    Job job = new Job(getConf(), "Q9EmpSalarySort");
    job.setJobName("Q9EmpSalarySort");

    // 设置 Mapper 和 Reduce 类
    job.setJarByClass(Q9EmpSalarySort.class);
    job.setMapperClass(MapClass.class);

    // 设置输出格式类
    job.setMapOutputKeyClass(IntWritable.class);
    job.setMapOutputValueClass(Text.class);
    job.setSortComparatorClass(DecreaseComparator.class);

    // 设置输入路径和输出路径
    String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
    FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
    FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

    // 等待作业完成并返回结果
    job.waitForCompletion(true);
    return job.isSuccessful() ? 0 : 1;
}

public static void main(String[] args) throws Exception {
    // 主方法，用于运行 MapReduce 作业    int res = ToolRunner.run(new Configuration(), new Q9EmpSalarySort(), args);
    System.exit(res);
}
```

总体来说，这个程序的实现过程包括以下几个步骤：

1. 定义 类，将输入数据映射为键值对，其中键为员工总收入，值为员工姓名。
2. 定义自定义的递减排序算法，用于对 Mapper 输出的键（员工总收入）进行降序排列。
3. 实现 Tool 接口的 run 方法，用于运行 MapReduce 作业，其中设置 Mapper 和 Reduce 类、输出格式类、输入路径和输出路径等参数。
4. 在主方法中运行 MapReduce 作业。

通过以上步骤，就能够实现对员工总收入进行降序排列的功能。









39.
    编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q9EmpSalarySort.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q9EmpSalarySort.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q9EmpSalarySort.java

编译代码：

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q9EmpSalarySort.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q9EmpSalarySort.jar ./Q9EmpSalary*.class
mv *.jar ../..
rm Q9EmpSalary*.class
请详细分析一下每一句话。
    
    这段代码的作用是编译并打包 Q9EmpSalarySort.java 程序代码。

首先，进入 /app/hadoop-1.1./myclass/class6 目录中，使用 vi 命令新建 Q9EmpSalarySort.java 程序代码，或者使用 /home/shiyanlou/install-pack/class6/Q9EmpSalarySort.java 文件。

然后，使用 javac 命令编译 Q9EmpSalarySort.java 程序代码。其中，-classpath 参数指定了编译时需要使用的类路径，包括 hadoop-core-1.1.2.jar 和 commons-cli-1.2.jar 两个 jar 包。

接着，使用 jar 命令将编译好的代码打成 jar。其中，cvf 参数表示创建新的 jar 包，Q9EmpSalarySort.jar 表示新建的 jar 包的名称，./Q9EmpSalary*.class 表示需要打包的文件。

最后，将打好的 包移动到上一级目录中，删除编译好的 class 文件。这样就完成了编译并打包 Q9EmpSalarySort.java 程序代码的过程。







40.
运行并查看结果

运行 Q9EmpSalarySort 运行的员工数据路径和输出路径两个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

员工数据路径：hdfs://hadoop:9000/class6/input/emp
输出路径：hdfs://hadoop:9000/class6/out9
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q9EmpSalarySort.jar Q9EmpSalarySort hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out9
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out9 目录。

hadoop fs -ls /class6/out9
hadoop fs -cat /class6/out9/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

5000    KING
3000    FORD
2975    JONES
2850    BLAKE
......
请详细分析一下每一句话。
    
    这段代码的作用是运行 Q9EmpSalarySort 程序，并查看运行结果。

首先，进入 /app/hadoop-1.1.2 目录中，使用 hadoop jar 命令行 Q9EmpSalarySort 程序。其中，Q9EmpSalarySort 表示程序的主类，hdfs://hadoop:9000/class6/input/emp 表示员工数据路径，hdfs://hadoop:9000/class6/out9 表示输出路径。

接着，使用 hadoop fs -ls 命令查看输出路径 /class6/out9 目录下的文件列表，确认程序运行成功。

最后，使用 hadoop fs -cat 命令查看 part-r-00000 文件的内容，即可查看程序运行结果。其中，part-r-00000 文件是程序的输出文件，包含了员工总收入和员工姓名的对应关系，按照员工总收入降序排列。







41.
问题分析

该公司所有员工可以形成入下图的树形结构，求两个员工的沟通的中间节点数，可转换在员工树中求两个节点连通所经过的节点数，即从其中一节点到汇合节点经过节点数加上另一节点到汇合节点经过节点数。例如求 M 到 Q 所需节点数，可以先找出 M 到 A 经过的节点数，然后找出 Q 到 A 经过的节点数，两者相加得到 M 到 Q 所需节点数。



在作业中首先在 Mapper 阶段所有员工数据，其中经理数据 key 为 0 值、value 为"员工编号，员工经理编号"，然后在 Reduce 阶段把所有员工放到员工列表和员工对应经理链表 Map 中，最后在 Reduce 的 Cleanup 中按照上面说所算法对任意两个员工计算出沟通的路径长度并输出。
请详细分析一下。
    
    这是一个典型的MapReduce问题，需要使用MapReduce框架来解决。在这个问题中，我们需要将员工数据转换为一张图，并使用图论算来求解两个员工之间的最短路径。

具体来说，我们可以在Mapper阶段将所有员工数据读入，并将经理数据key设置为0，value设置为"员工编号，员工经理编号"。然后，在Reduce阶段，我们可以将所有员工放到员工和员工对应经理链表Map中。在这个Map中，每个键表示一个员工，对应的值是一个列表，其中包含该员工的所有下属员工。

接下来，在Reduce的Cleanup阶段，我们可以使用图论法来计算任意两个员工之间的最短路径。具体来说，我们可以使用广度优先搜索算法（BFS）来求解最短路径。BFS算法从起点开始，逐层遍历图中的节点，直到找到目标节点为止。在遍历过程中，我们需要记录每个节点的深度（即从起点到该节点的距离），以便在找到目标节点后计算最短路径。

在这个问题中，我们可以将员工列表和员工对应经理链表Map转换为一张无向图，其中每个节点表示一个员工，每个边表示两个员工之间关系。然后，我们可以使用BFS算法来求解两个员工之间的最短路径。具体来说，我们可以从其中一个员工开始，逐层遍历图中的节点，直到找到另一个员工为止。在遍历过程中，我们需要记录每个节点的深度，以便在找到目标节点后计算最短路径。

需要注意的是，如果两个员工之间没有直接的关系，那么它之间的最短路径就是它们到共同祖先节点的距离之和。因此，在实际求解中，我们需要先找到这两个员工的共同祖先节点，然后再计算它们到共同祖先节点的距离。最后，我们可以将计算出的沟通路径长度输出。








42.
import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.NullWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;

public class Q10MiddlePersonsCountForComm extends Configured implements Tool {

    public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {

        public void map(LongWritable key, Text value, Context context) throws IOException,         InterruptedException {

            // 对员工文件字段进行拆分
            String[] kv = value.toString().split(",");

            // 输出key为0和value为员工编号+","+员工经理编号
            context.write(new IntWritable(0), new Text(kv[0] + "," + ("".equals(kv[3]) ? " " : kv[3])));
        }
    }

    public static class Reduce extends Reducer<IntWritable, Text, NullWritable, Text> {

        // 定义员工列表和员工对应经理Map
        List<String> employeeList = new ArrayList<String>();
        Map<String, String> employeeToManagerMap = new HashMap<String, String>();

        public void reduce(IntWritable key, Iterable<Text> values, Context context) throws         IOException, InterruptedException {

            // 在reduce阶段把所有员工放到员工列表和员工对应经理Map中
            for (Text value : values) {
                employeeList.add(value.toString().split(",")[0].trim());
                employeeToManagerMap.put(value.toString().split(",")[0].trim(),                             value.toString().split(",")[1].trim());
            }
        }

        @Override
        protected void cleanup(Context context) throws IOException, InterruptedException {
            int totalEmployee = employeeList.size();
            int i, j;
            int distance;
            System.out.println(employeeList);
            System.out.println(employeeToManagerMap);

            // 对任意两个员工计算出沟通的路径长度并输出
            for (i = 0; i < (totalEmployee - 1); i++) {
                for (j = (i + 1); j < totalEmployee; j++) {
                    distance = calculateDistance(i, j);
                    String value = employeeList.get(i) + " and " + employeeList.get(j) + " =                     " + distance;
                    context.write(NullWritable.get(), new Text(value));
                }
            }
        }

        /**
         * 该公司可以由所有员工形成树形结构，求两个员工的沟通的中间节点数，可以转换在员工树中两员工之间的距离
         * 由于在树中任意两点都会在某上级节点汇合，根据该情况设计了如下算法
         */
        private int calculateDistance(int i, int j) {
            String employeeA = employeeList.get(i);
            String employeeB = employeeList.get(j);
            int distance = 0;

            // 如果A是B的经理，反之亦然
            if (employeeToManagerMap.get(employeeA).equals(employeeB) ||                                     employeeToManagerMap.get(employeeB).equals(employeeA)) {
                distance = 0;
            }
            // A和B在同一经理下
            else if  (employeeToManagerMap.get(employeeA).equals(
                    employeeToManagerMap.get(employeeB))) {
                distance = 0;
            } else {
                // 定义A和B对应经理链表
                List<String> employeeA_ManagerList = new ArrayList<String>();
                List<String> employeeB_ManagerList = new ArrayList<String>();

                // 获取从A开始经理链表
                employeeA_ManagerList.add(employeeA);
                String current = employeeA;
                while (false == employeeToManagerMap.get(current).isEmpty()) {
                    current = employeeToManagerMap.get(current);
                    employeeA_ManagerList.add(current);
                }

                // 获取从B开始经理链表
                employeeB_ManagerList.add(employeeB);
                current = employeeB;
                while (false == employeeToManagerMap.get(current).isEmpty()) {
                    current = employeeToManagerMap.get(current);
                    employeeB_ManagerList.add(current);
                }

                int ii = 0, jj = 0;
                String currentA_manager, currentB_manager;
                boolean found = false;

                // 遍历A与B开始经理链表，找出汇合点计算
                for (ii = 0; ii < employeeA_ManagerList.size(); ii++) {
                    currentA_manager = employeeA_ManagerList.get(ii);
                    for (jj = 0; jj < employeeB_ManagerList.size(); jj++) {
                        currentB_manager = employeeB_ManagerList.get(jj);
                        if (currentA_manager.equals(currentB_manager)) {
                            found = true;
                            break;
                        }
                    }

                    if (found) {
                        break;
                    }
                }

                // 最后获取两只之前的路径
                distance = ii + jj - 1;
            }

            return distance;
        }
    }

    @Override
    public int run(String[] args) throws Exception {

        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q10MiddlePersonsCountForComm");
        job.setJobName("Q10MiddlePersonsCountForComm");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q10MiddlePersonsCountForComm.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置Mapper输出格式类
        job.setMapOutputKeyClass(IntWritable.class);
        job.setMapOutputValueClass(Text.class);

        // 设置Reduce输出键和值类型
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(NullWritable.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为员工数据路径和第2个参数为输出路径
        String[] otherArgs = new GenericOptionsParser(job.getConfiguration(),                     args).getRemainingArgs();
        FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q10MiddlePersonsCountForComm(), args);
        System.exit(res);
    }
}
请详细分析一下每一句代码。
    
    这段代码是一个基于Hadoop的MapReduce程序，用于计算公司中任意两个员工之间的沟通路径长度。

导入必要的包和类库
java
import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.LongWritable;
import org.apache.hadoop.io.NullWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
定义Map类
java
public static class MapClass extends Mapper<LongWritable, Text, IntWritable, Text> {
    public void map(LongWritable key, Text value, Context context) throws IOException, InterruptedException {
        // 对员工文件字段进行拆分
        String[] kv = value.toString().split(",");
        // 输出key为0和value为员工编号+","+员工经理编号
        context.write(new IntWritable(0), new Text(kv[0] + "," + ("".equals(kv[3]) ? " " : kv[3])));
    }
}
Mapper将员工数据中的每行记录转化为一个<key, value>对，其中key为0，value格式为"员工编号,员工经理编号"。这里使用了LongWritable和Text类型来表示输入数据，使用IntWritable和Text类型来表示Mapper输出数据。

定义Reduce类
java
public static class Reduce extends Reducer<IntWritable, Text, NullWritable, Text> {
    // 定义员工列表和员工对应经理Map
    List<String> employeeList = new ArrayList<String>();
    Map<String, String> employeeToManagerMap = new HashMap<String, String>();

    public void reduce(IntWritable key, Iterable<Text> values, Context context) throws IOException, InterruptedException {
        // 在reduce阶段把所有员工放到员工列表和员工对应经理Map中
        for (Text value : values) {
            employeeList.add(value.toString().split(",")[0].trim());
            employeeToManagerMap.put(value.toString().split(",")[0].trim(), value.toString().split(",")[1].trim());
        }
    }

    @Override
    protected void cleanup(Context context) throws IOException, InterruptedException {
        int totalEmployee = employeeList.size();
        int i, j;
        int distance;
        System.out.println(employeeList);
        System.out.println(employeeToManagerMap);

        // 对任意两个员工计算出沟通的路径长度并输出
        for (i = 0; i < (totalEmployee - 1); i++) {
            for (j = (i + 1); j < totalEmployee; j++) {
                distance = calculateDistance(i, j);
                String value = employeeList.get(i) + " and " + employeeList.get(j) + " =" + distance;
                context.write(NullWritable.get(), new Text(value));
            }
        }
    }

    /**
     * 该公司可以由所有员工形成树形结构，求两个员工的沟通的中间节点数，可以转换在员工树中两员工之间的距离
     * 由于在树中任意两点都会在某上级节点汇合，根据该情况设计了如下算法
     */
    private int calculateDistance(int i, int j) {
        String employeeA = employeeList.get(i);
        String employeeB = employeeList.get(j);
        int distance = 0;

        // 如果A是B的经理，反之亦然
        if (employeeToManagerMap.get(employeeA).equals(employeeB) || 
            employeeToManagerMap.get(employeeB).equals(employeeA)) {
            distance = 0;
        }
        // A和B在同一经理下
        else if  (employeeToManagerMap.get(employeeA).equals(employeeToManagerMap.get(employeeB))) {
            distance = 0;
        } else {
            // 定义A和B对应经理链表
            List<String> employeeA_ManagerList = new ArrayList<String>();
            List<String> employeeB_ManagerList = new ArrayList<String>();

            // 获取从A开始经理链表
            employeeA_ManagerList.add(employeeA);
            String current = employeeA;
            while (false == employeeToManagerMap.get(current).isEmpty()) {
                current = employeeToManagerMap.get(current);
                employeeA_ManagerList.add(current);
            }

            // 获取从B开始经理链表
            employeeB_ManagerList.add(employeeB);
            current = employeeB;
            while (false == employeeToManagerMap.get(current).isEmpty()) {
                current = employeeToManagerMap.get(current);
                employeeB_ManagerList.add(current);
            }

            int ii = 0, jj = 0;
            String currentA_manager, currentB_manager;
            boolean found = false;

            // 遍历A与B开始经理链表，找出汇合点计算
            for (ii = 0; ii < employeeA_ManagerList.size(); ii++) {
                currentA_manager = employeeA_ManagerList.get(ii);
                for (jj = 0; jj < employeeB_ManagerList.size(); jj++) {
                    currentB_manager = employeeB_ManagerList.get(jj);
                    if (currentA_manager.equals(currentB_manager)) {
                        found = true;
                        break;
                    }
                }

                if (found) {
                    break;
                }
            }

            // 最后获取两只之前的路径
            distance = ii + jj - 1;
        }

        return distance;
    }
}
Reduce类将所有employee数据写入两个变量employeeList和employeeToManagerMap中，并实现了cleanup方法，用于输出任意两个员工之间的沟通路径长度。这里使用了IntWritable和Text类型来表示Reducer输入数据，使用NullWritable和Text类型来表示Reducer输出数据。

实现Tool接口
java
public class Q10MiddlePersonsCountForComm extends Configured implements Tool {
    @Override
    public int run(String[] args) throws Exception {
        // 实例化作业对象，设置作业名称
        Job job = new Job(getConf(), "Q10MiddlePersonsCountForComm");
        job.setJobName("Q10MiddlePersonsCountForComm");

        // 设置Mapper和Reduce类
        job.setJarByClass(Q10MiddlePersonsCountForComm.class);
        job.setMapperClass(MapClass.class);
        job.setReducerClass(Reduce.class);

        // 设置Mapper输出格式类
        job.setMapOutputKeyClass(IntWritable.class);
        job.setMapOutputValueClass(Text.class);

        // 设置Reduce输出键和值类型
        job.setOutputFormatClass(TextOutputFormat.class);
        job.setOutputKeyClass(NullWritable.class);
        job.setOutputValueClass(Text.class);

        // 第1个参数为员工数据路径和第2个参数为输出路径
        String[] otherArgs = new GenericOptionsParser(job.getConfiguration(), args).getRemainingArgs();
        FileInputFormat.addInputPath(job, new Path(otherArgs[0]));
        FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

        job.waitForCompletion(true);
        return job.isSuccessful() ? 0 : 1;
    }

    /**
     * 主方法，执行入口
     * @param args 输入参数
     */
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new Q10MiddlePersonsCountForComm(), args);
        System.exit(res);
    }
}
该接口实现了run方法，其中Job类实例化后设置了Mapper、Reducer类以及输入输出格式等参数，并指定输入输出路径。ToolRunner类则负责执行Hadoop作业。同时，在main方法中可以直接运行该类。

总体来说，该程序主要是对员工数据进行Map操作，然后将结果传递给Reduce处理。最终输出任意两个员工之间的沟通路径长度。
    







43.

编译并打包代码

进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q10MiddlePersonsCountForComm.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q10MiddlePersonsCountForComm.java 文件）。

cd /app/hadoop-1.1.2/myclass/class6
vi Q10MiddlePersonsCountForComm.java

编译代码

javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q10MiddlePersonsCountForComm.java

把编译好的代码打成 jar 包，如果不打成 jar 形式运行会提示 class 无法找到的错误。

jar cvf ./Q10MiddlePersonsCountForComm.jar ./Q10MiddlePersons*.class
mv *.jar ../..
rm Q10MiddlePersons*.class
请详细分析一下每一句话。
    
    
    这段代码是在Linux系统下使用Hadoop框架编译并打包Java程序的过程。下面是每一句话的详细解释：

1. 进入 /app/hadoop-1.1.2/myclass/class6 目录中新建 Q10MiddlePersonsCountComm.java 程序代码（代码也可以使用 /home/shiyanlou/install-pack/class6/Q10MiddlePersonsCountForComm.java 文件）。

这句话的作用是进入指定目录，并在该目录下新建一个Java程序文件Q10MiddlePersonsCountForComm.java。如果该目录下已经存在该文件，则可以使用指定路径下的文件。

2. cd /app/hadoop-1.1.2/myclass/class6

这句话的作用是进入指定目录。

3. vi Q10MiddlePersonsCountForComm.java

这句话的作用是使用vi编辑器开指定的Java程序文件，以便进行编辑。

4. javac -classpath ../../hadoop-core-1.1.2.jar:../../lib/commons-cli-1.2.jar Q10MiddlePersonsCountForComm.java

这句话的作用是使用javac编译指定的Java程序文件，并指定编译时需要使用的类路径。其中，-classpath参数指了需要使用的类路径，../../hadoop-core-1.1.2.jar和../../lib/commons-cli-1.2.jar是需要使用的类库文件，Q10MiddlePersonsCountForComm.java是需要编译的Java程序文件。

5. cvf ./Q10MiddlePersonsCountForComm.jar ./Q10MiddlePersons*.class

这句话的作用是使用jar命令将编译好的Java程序文件打包成jar文件。其中，cvf参数表示创建新的jar文件./Q10MiddlePersonsCountForComm.jar是指定的jar文件名，./Q10MiddlePersons*.class是指定需要打包的Java程序文件。

6. mv *.jar ../..

这句话的作用是将打包好的jar文件移动到上一级目录中。

7. rm Q10MiddlePersons*.class

这句话的作用是删除编译好的Java程序文件，以便下一次编译。






44.

运行并查看结果

运行 Q10MiddlePersonsCountForComm 运行的员工数据路径和输出路径两个参数，需要注意的是 hdfs 的路径参数路径需要全路径，否则运行会报错：

员工数据路径：hdfs://hadoop:9000/class6/input/emp。
输出路径：hdfs://hadoop:9000/class6/out10。
运行如下命令：

cd /app/hadoop-1.1.2
hadoop jar Q10MiddlePersonsCountForComm.jar Q10MiddlePersonsCountForComm hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out10
运行成功后，刷新 CentOS HDFS 中的输出路径 /class6/out10 目录。

hadoop fs -ls /class6/out10
hadoop fs -cat /class6/out10/part-r-00000

打开 part-r-00000 文件，可以看到运行结果：

7369 and 7499 = 4
7369 and 7521 = 4
7369 and 7566 = 1
7369 and 7654 = 4
7369 and 7698 = 3
......
请详细分析每一句话。
    
    
    这段代码是在Linux系统下使用Hadoop框架运行Java程序并查看结果的过程。下面是每一句话的详细解释：

1. cd /app/hadoop-11.2

这句话的作用是进入指定目录。

2. hadoop jar Q10MiddlePersonsCountForComm.jar Q10MiddlePersonsCountFor hdfs://hadoop:9000/class6/input/emp hdfs://hadoop:9000/class6/out10

这句话的作用是使用hadoop命令运行指定的Java程序，并指定程序需要使用的输入路径和输出路径。其中，hadoop jar命令表示使用Hadoop框架运行Java程序，Q10MiddlePersonsCountForComm.jar是指定的Java程序文件，Q10MiddlePersonsCountForComm是指定的Java程序类名，hdfs://hadoop:9000/class6/input/emp是指定的输入路径，h://hadoop:9000/class6/out10是指定的输出路径。

3. hadoop fs -ls /class6/out10

这句话的作用是使用hadoop fs命令查看指定路径下的文件列表。其中，-ls参数表示列出指定路径下的文件列表，class6/out10是指定的路径。

4. hadoop fs -cat /class6/out10/part-r-00000

这句话的作用是使用hadoop fs命令查看指定文件的内容。其中，-cat参数表示查看指定文件的内容，/class6/out10/part-r00000是指定的文件路径。






45.








46.









47.








48.









49.








50.












51.





52.





53.







54.






55.






56.






57.






58.






59.








60.







61.






62.









63.







64.








65.






66.






67.







68.






69.






70.







71.







72.








73.







74.






75.






76.







77.






78.






79.






80.







81.







82.








83.







84.








85.







86.






87.








88.






89.







90.






91.






92.






93.







94.







95.







96.






97.






98.






99.






100.



