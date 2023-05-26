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








22.








23.








24.








25.








26.








27.









28.








29.








30.








31.









32.








33.








34.








35.








36.








37.









38.









39.







40.








41.









42.








43.








44.








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



